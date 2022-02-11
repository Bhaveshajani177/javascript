# Different Form Fields Validation

## Validate Phone Number
- Valid formats:
  - (123) 456-7890
  - (123)456-7890
  - 123-456-7890
  - 123.456.7890
  - 1234567890
  - +31636363634
  - 075-63546725
  <br />
  
  ```js
  function validatePhoneNo(number) {
      let regex = /^[\+]?[(]?[0-9]{3}[)]?[-\s\.]?[0-9]{3}[-\s\.]?[0-9]{4,6}$/im;
      return regex.test(number);
  }

  let phoneNo = "1234567890";
  validatePhoneNo(phoneNo);
  ```
  
## Validate Email
  ```js
  const validateEmail = (email) => {
      let regex = /^(([^<>()[\]\\.,#;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      return regex.test(String(email).toLowerCase());
  };

  validateEmail("abc.def@mail.com");
  ```
