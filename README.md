# Add-Seperator-after-typing-every-2-character-automatically
This function is used to add Seperator (Like "12/12/2000") in TextField


* Add delgate method UITextFieldDelegate in your class
* Connect Textfield to Delegate . 
* Then use Below Code to acheive format like this . (12/12/2000) (Date of Bith Format) 

```swift

    func textField(_ textField: UITextField, shouldChangeCharactersIn range: NSRange, replacementString string: String) -> Bool {
        let text = (textField.text! as NSString).replacingCharacters(in: range, with: string)
        let count = text.count
        if string != "" {
            if count > 6
            {
                return true
            }
            if count % 3 == 0  {
                dateOfBirthTextField.text?.insert("/", at: String.Index.init(encodedOffset: count - 1))
            }
            return true
        }
        return true
    }

```

* Output Will be Like this 
```swift

//Date of Birth Format

12/12/2000  //This will be typed in textfiled after adding the above function.

```
