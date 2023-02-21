# NOTEBOOK

> NOTE FOR IOS

1. Scale image in xcode
![plot](./image/277687562_665811971191641_7304645768922870394_n.png)


2. Get title of button
    @IBAction func choiceMade(_ sender: UIButton) {
        `sender.currentTitle`
    }

3. How to get value of slider
    @IBAction func heightSliderChanged(_ sender: UISlider) {
        `print(sender.value)`
    }

4. Get decimal after point
    `print(String(format: "%.0f", value))` or `Int(value)`  without decimal
    `print(String(format: "%.2f", value))` get 2 decimal after point

5. How to set text
    `weightLabel.text = "\(weight)kg"`

6. How to create a class

class Enemy{
    var health = 100
    var attackStrenght = 10
    
    func move(){
        print("Walk forwards.")
    }
    
    func attack(){
        print("Land a hit, does \(attackStrenght) damage.")
    }
}


7. `override` inside a class
class Dragon: Enemy {    
    override func move(){
        `super.move()` we could use this if we want hermitage from parent class  
        print("Dragon Walk forwards123.")
    }
} 

8. Structs are Passed by Value
   Classes are Passed by Reference


9. How to navigation to other screen
        let secondVC = SecondViewController()
        secondVC.bmiValue = String(format: "%.1f", bmi)
        self.present(secondVC, animated: true, completion: nil)

10.  `self.dismiss(animated: true, completion: nil)` => return back to previous screen

11. How to change name file or class
click right -> Refactor -> Rename

12. Optional Binding
    1. Force Unwrapping => `optional!` 
    2. Check for nil value 
        => 
    ```swift
        if optional != nil {
            optional!
        }
    ```
    3. Optional Binding
        => 
    ```swift
        if let safeOptional = optional {
            safeOptional
        }
    ```
    4. Nil Coalescing operator
        => `optional ?? defaultValue`
    5. Optional Chaining
        => `optional?.property`
        => `optional?.method()`


13. UITextField
    `textInput.endEditing(true)` => dismiss the keyboard


14. Heritage class from UITextFieldDelegate => so that we can use `searchTextField.delegate = self`

add `func textFieldShouldReturn`  ==> fired when press go on keyboard 

`func textFieldDidEndEditing` ==> when user end up with editing input text

`func textFieldShouldEndEditing` ==> we can check if text input = "" we can announcement that user still not yet input anything and return false so that `textFieldShouldReturn` will not run


15. Fix `unsupported os version xcode`
`https://github.com/iGhibli/iOS-DeviceSupport/tree/master/DeviceSupport`