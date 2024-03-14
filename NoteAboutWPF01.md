### 0125 Valid Palindrome

#### PropertyChangedEventHandler 
public event PropertyChangedEventHandler PropertyChanged;
private void NotifyPropertyChanged([CallerMemberName] string name = "")
{
    PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(name));
}

- `이벤트`: 클래스나 객체에서 발생하는 특정한 사건을 나타냅니다. .NET에서 이벤트는 델리게이트 타입을 사용하여 정의되며, 이벤트에 메서드를 구독하거나 구독 해제할 수 있습니다. 
          이벤트는 그것을 선언한 클래스나 객체의 외부에서 직접 발생시킬 수 없고, 오직 그 클래스나 객체 내부에서만 발생시킬 수 있습니다(캡슐화).
- `델리게이트`: 메서드에 대한 참조를 보유하는 타입이며 델리게이트타입의 변수에 메서드를 할당해 그 변수를 통해 메서드를 호출할 수 있습니다.


***

