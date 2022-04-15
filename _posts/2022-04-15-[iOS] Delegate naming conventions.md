---
title: '[iOS] Delegate naming conventions'
categories:
  - iOS
  - Swift

comments: true 
---



delegate 프로토콜은 일반적으로 클래스 선언과 밀접하게 연결되며 클래스가 없으면 대리자를 사용할 수 없다. 
Swift나 Objective-C도 중첩 프로토콜 선언을 허용하지 않는다. 
> 따라서 delegate 프로토콜의 이름은 **클래스 이름**으로 시작해야 한다.

~~~ swift
class UIScrollView
protocol UIScrollViewDelegate

class UITextField
protocol UITextFieldDelegate

class UIApplication
protocol UIApplicationDelegate
~~~


> 메소드 이름은 접두사 없이 **클래스 이름**으로 시작하고, 첫번재 인수는 위임 개체 자체여야 한다.

~~~ swift
func scrollViewDidScroll(_ scrollView: UIScrollView)

func textFieldShouldBeginEditing(_ textField: UITextField) -> Bool

func applicationDidFinishLaunching(_ application: UIApplication)
~~~


> 이를 통해 기본값을 제공하거나 여러 위임 개체를 처리할 때, 다시 참조할 수 있고 유용하다.

~~~ swift
extension MyViewController: UITableViewDelegate {
    func tableView(_ tableView: UITableView, heightForRowAt indexPath: IndexPath) -> CGFloat {
        if indexPath.row == tallRow {
            return 142.0
        }
        
        return tableView.rowHeight
    }
}

extension MyViewController: UITextFieldDelegate {
    func textFieldDidEndEditing(_ textField: UITextField, reason: UITextFieldDidEndEditingReason) {
        guard reason == .committed else {
            return
        }
        
        switch textField {
            case emailTextField:
                email = textField.text
            case passwordTextField:
                password = textField.text
       
            default:
                break
            }
        }
    }
}
~~~


> 메소드 이름에는 발생했거나 임박한 이벤트를 식별하기 위한 **보조 동사(should, will, has, did)**가 포함되어야 한다.

~~~swift
// 드래그가 시작될 때, 호출됨.
func scrollViewWillBeginDragging(_ scrollView: UIScrollView)

// 유저가 스크롤을 상단으로 올렸을 때, true가 반환됨.
func scrollViewShouldScrollToTop(_ scrollView: UIScrollView) -> Bool

// 스크롤 애니메이션이 끝났을 때, 호출됨.
func scrollViewDidScrollToTop(_ scrollView: UIScrollView)
~~~


> 대리자가 임박한 이벤트를 변경하거나 추가 정보를 제공하는 경우에는 예외가 일반적이다.

~~~swift
protocol UIScrollViewDelegate {
    func viewForZooming(in scrollView: UIScrollView) -> UIView?
}

protocol UITableViewDelegate {
    func indexPathForPreferredFocusedView(in tableView: UITableView) -> IndexPath?
}

protocol UIApplicationDelegate {
    var window: UIWindow? { get set }
}
~~~

---
### 참고 자료
- <a href = "https://dmytro-anokhin.medium.com/delegate-in-swift-47b3d6fcecc3"> Delegate in Swift </a>