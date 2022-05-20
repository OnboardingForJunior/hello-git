# branch란?

#### 목차
</br>
- branch
- checkout
- merge

## branch

git은 Staging Area에 있는 모든 데이터 커밋 메세지 등의 포인터를 포함하는 개체를 커밋을 통해 저장한다. branch는 이러한 커밋 사이를 가볍게 이동할 수 있는 포인터와 같다. 기본적으로 Git은 master 브랜치를 생성한다.

### 포인터(pointer)

다른 변수 혹은 그 변수의 메모리 공간주소를 가리키는 변수 !

## checkout

현재 브랜치를 떠나 새로운 브랜치로 들어간다는 뜻이다. 브랜치 간 이동할때 이 명령어를 쓴다. </br>
$ git checkout 브랜치이름

## merge

브랜치를 하나로 합치는 것을 뜻한다. 현재 브랜치에 다른 브랜치를 병합한다. </br>
공동 작업시 쉽게 쓰인다.

## Pull Request

Push <-> Pull : 깃 서버에 업데이터 되어 있는 내용을 받아오는것.

#### Pull과 Pull Request의 차이점

Pull은 개인 서버에서 개인 로컬 컴퓨터로 받아오려는 목적!
</br>
Pull Request는 원본 저장소의 내용을 Fork 하는 경우 다른사람의 저장소 내용을 업데이트 후 작업내용을 원본저장소에 적용해주도록 하는 요청을 보낸다.
</br>
원본작성자가 승인을 하면 반영이 된다. merge confirm 하거나 Reject(거부)할 수 있다.
- Fork : 다른사람의 github repository를 복제하여 수정 추가 삭제를 용이하게 해줌. 원본과 연결되어 있어 fetch, rebase 과정을 통해 그대로 반영할 수 있음