## 동기(Synchronous) 블로킹, 동기 논블로킹

- 동기란? 호출과 리턴이 순차적으로 진행되는것.

- 블로킹이란? 제어권을 양도하는것과 같다. (제어권을 빼앗긴 함수는 멈춤상태가 됨)

- 논블로킹이란? 제어권을 양도하지 않아요.

- 동기 블로킹 : A실행시 B를 호출과 동시에 B에게 제어권을 넘긴다할때, A는 제할일을 못하고 대기!

- 동기 블로킹의 예시

	- help!!

- 동기 논블로킹의 예시
```
function runSync(result) {
	return result = '서버에서 온 사람입니다';
}

const cb1 = result => {
	console.log('누구세요? :', result);
};

function main() {
	const syncObj = runSync();
	cb1(syncObj);
	console.log('함수는 종료');
}

main();

// main함수에서 cb1에 할당받은 콜백함수로 넘어가지만 main은 미완료이므로 수행중임. 콜백함수 끝나며 main은 종료.
```

- 동기 논블로킹 : A실행시 B를 호출 리턴하면서 A가 자신을 실행시킬 수 있음. 

## 비동기(Asynchronous) 블로킹, 비동기 논블로킹

- 비동기란? 콜백함수를 호출하여 동시다발적으로 작업을 할 수 있도록 해주는것.</br>
	- 대표적인 비동기적 API로 setTimeout()

- 콜백함수란? 함수가 자신의 변수로 불러온 함수! A함수가 B를 콜백함수로 썼다면, B는 A안에서만 실행된다.
	1. 다른 함수의 인자로써 이용되는 함수.
	2. 어떤 이벤트에 의해 호출되어지는 함수.

- 비동기 블로킹 : A실행시 B를 호출과 동시에 B에게 제어권도 콜백함수도 넘겨버림. A는 아무것도 못하고 B만 기다리게됨!

- 비동기 논블로킹 : A실행시 B를 호출과 동시에 B에게 콜백함수를 넘김. A가 제할일 하면서 B는 자신이 끝난후에 콜백을 실행시킴!

- 비동기 블로킹의 예시
```
function runAsync(time) {
	return new Promise(resolve => {
		setTimeout(() => {
			resolve('서버에서 온 사람입니다');
		}, time);
	});
}

const cb1 = result => {
	console.log('누구세요? :', result);
};

async function main() {
	const asyncObj = await runAsync();
	cb1(asyncObj);
	console.log('함수는 종료');
}

main();

// Promise에 값이 충족될때까지 async 함수의 실행을 일시 정지하고, Promise에 값이 충족되면 async 함수를 일시 정지한 부분부터 실행합니다.
// 비동기 상황임에도 제어를 넘기기 때문에 순차적으로 진행하는것 처럼 보입니다.
```

- 비동기 논블로킹의 예시
```
function runAsync(time) {
	return new Promise(resolve => {
		setTimeout(() => {
			resolve('서버에서 온 사람입니다');
		}, time);
	});
}

const cb1 = result => {
	console.log('누구세요? :', result);
	return runAsync2(3000);
};

function main() {
	const asyncObj = runAsync(1000);
	asyncObj.then(cb1).then(cb2);
	console.log('함수는 종료');
}

main();

// promise로 인한 비동기상황
```
