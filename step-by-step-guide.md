
#### Steps for python beginners:
1. Create a test file called `test_string_mummifier.py` (You will use this file to write tests for your solution)

   1. Create a python class `TestStringMummifier` that inherits from TestCase and import the necessary library
   
   ```python
   from unittest import TestCase
   
   class StringMummifierTestCase(TestCase):
       pass
   ```
   
   2. Create a method prefixed with `test_` (this because the unittest framework picks up only test methods beginning with `test_`
Your test method should have a meaningful name describing the scenario you are testing and its expected behaviour if possible. For e.g. `test_should_not_mummify_empty_string`

   ```python
   from unittest import TestCase
   
   class StringMummifierTestCase(TestCase):
       def test_should_not_mummify_empty_string(self):
           pass
   ```

   3. In the test method, we usually structure tests in the following manner:
      1. Initialize any variables you require (Arrange)
      2. Invoke the method you are testing (Act)
      3. Check that your expectations are met (Assert)
         
         - Tip: Utilise the unittest's `self.assertEqual` to validate the method’s outputs against what you expect
   
   - “Arrange, Act, Assert” (aka “AAA”) is a very simple way to structure your tests. It is especially helpful when learning the ropes.
   
   - Since this is the very first test we create and the actual method has not been created yet, you may not know the:
      1. class to call
      2. method to call
      3. method signature

      Writing tests first would allow you to think about how you wish to design and use the actual method. 

      In our case, let's say we wish to put the method in a new class called `StringMummifier`. And we would like to call the method `mummify`, since that describes what it does. The method could take in a word and output the mummified word.

    ```python
    from unittest import TestCase
    
    from string_mummifier import StringMummifier
    
    class StringMummifierTestCase(TestCase):
        def test_should_not_mummify_empty_string(self):
            # Arrange
            word = ""
    
            # Act
            mummifier = StringMummifier()
            mummified_word = mummifier.mummify(word)
    
            # Assert
            self.assertEqual("", mummified_word)
    ```
    
    4. Run the test 
    
       In your project folder, you can run `python3 -m unittest test_string_mummifier.py`
       
       Or if you are using an IDE like PyCharm, you should be able to run tests from the IDE itself by right clicking the test method name and selecting 'Run unittests for ...'
    
    You would see that now would throw the below error: 
    
    `ImportError: cannot import name 'StringMummifier'`
    
    This is because we've not implemented the class yet! Let's do that now.

2. Create a file called `string_mummifier.py` (You will use this file to write the code for your solution)

   1. Create a python class `StringMummifier` and a method in the class called `mummify` that takes in a word. For now let's just make the method return None.
    
    ```python
    class StringMummifier:
        def mummify(self, word):
            return None
    ```

3. Run the test

   In your project folder, you can run `python3 -m unittest test_string_mummifier.py`
  
   See that the test fails for the right reason. (Red Stage!) You should get a similar error as below:
    
   `AssertionError: '' != None`
    
   
4. Fix the test by implementing the simplest possible logic in the mummify method in order to pass the test.

   ```python
   class StringMummifier:
       def mummify(self, word):
           return ""

   ```

5. Run the test

   1. See that the test passes (Green Stage!)

6. Refactor your solution if required

7. Continue repeating the below steps:
   1. Writing a new test for another test scenario, see that it fails (Red)
   2. Write the functionality to fix the test, and that all tests should still pass (Green)
   3. Refactor where necessary

  