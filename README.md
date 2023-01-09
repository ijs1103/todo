# todo

![Simulator Screen Recording - iPod touch (7th generation) - 2023-01-10 at 02 10 13](https://user-images.githubusercontent.com/42196410/211366556-1396615f-b9d3-46a6-aa38-741097108eca.gif)


## 🧩 개요

코어데이터로 todo를 생성 및 삭제

## 🤔 배운 내용

### ✔️ 세그웨이

세그웨이를 통한 화면전환 및 데이터 전달

### ✔️ 코어데이터

코어데이터로 CRUD 하기

### ✔️ 특정 버튼을 눌렀을 때 화면전환 하는법

``` 
cell.updateButtonPressed = { [weak self] (senderCell) in
  // 뷰컨트롤러에 있는 세그웨이의 실행
  self?.performSegue(withIdentifier: "ToDoCell", sender: indexPath)
}
        
```
`UITableViewCell`에서 클로저를 담는 저장속성을 선언하고, `viewController`에서 세그웨이가 실행되는 로직을 해당 클로저에 담아주고, `UITableViewCell`에서 다시 이 클로저를 실행하는 방식.

이때 클로저는 `UITableViewCell`인 `self`를 참조하고, 강한 순환 참조를 방지하기 위하여 캡처리스트의 약한 참조(`[weak self]`)를 한다. 약한참조를 함으로써 self가 가리키는 참조타입의 reference count를 증가시키지 않는다.

### ✔️ cornerRadius를 너비나 높이를 기준으로 설정하고 싶을때 

View의 Drawing Cycle 중 `viewDidLayoutSubviews` 시점에 cornerRadius를 세팅 해준다.


### ✔️ TextView의 placeholder

TextView의 placeholder는 따로 존재하지 않기 때문에, `UITextViewDelegate` 프로토콜에서 직접 구현한다.

