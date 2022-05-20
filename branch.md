# branch란?

목차
</br>
- branch
- checkout
- merge
- Github flow

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

## Github flow

Github에서 제안하는 프로젝트 관리 방법을 뜻한다. 브랜치와 Pull Request를 사용하는것이 특징이다. </br>
1. document branch 생성 </br>
2. 수정을 통해 변화를 준다.  </br>
3. pull request를 만든다.  </br>
3. 검토자는 pull request에 대한 코멘트를 단다.  </br>
4. Pull Request를 병합한다. </br>
5. document branch 삭제 </br>