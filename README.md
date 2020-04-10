## Python_Basics
Python Basic Program

## Question 1: First Non-Unique word in a String
Given String, Find the first repeating words in it and return the words. If it doesn't exist, raise value error

#### Method 1: using string

```python3

def parent_word(string: str) -> bool:
    
    #Split the string into words using built-in function
    for word in string.split():
        if string.count(word) != 1:
            return word
            break
            
    raise ValueError('no repeated word found')
    
```

#### Method 2: using set

```python3

def parent_word(string: str) -> bool:
    processed_word = set()
    
    #Split the string into words using built-in function
    for word in string.split():
        if word in processed_word:
            return word
            break
    processed_word.add(word)
        
    raise ValueError('no repeated word found')
    
```

#### Method 3: using list

```python3

def parent_word(string: str) -> bool:
    processed_word = []
    
    #Split the string into words using built-in function  
    for word in string.split():
        if word in processed_word:
            return word
            break
    processed_word.append(word)
        
    raise ValueError('no repeated word found')
    
```

#### Method 4: 

```python3

def parent_word(string: str) -> bool:
    #Converts the string into lowercase  
    string = string.lower()
    
    #Split the string into words using built-in function
    words = string.split()
    
    for i in range(0, len(words)):
        count = 1
        for j in range(i+1, len(words)):
        
            # Checking the extact matching word
            if(words[i] == (words[j])):
                count = count + 1
                
                #Set words[j] to 0 to avoid printing visited word  
                words[j] = "0"
                
        #Displays the duplicate word if count is greater than 1  
        if(count > 1 and words[i] != "0"):  
            return words[i] 
        
    raise ValueError('no repeated word found')
    
```

#### Output

```shell
string = "python is the best best programming language"
 
parent_word(string)

'best'

```

## Question 2: Print particular string when given number multiplies of 2 and 3 based on below conditions 
1. "Dexter" when number is multiple of 2
2. "The Mentalist" when number is multiple of 3
3. "Mind Hunters" when number is multiple of 2 and 3
               
               
```python3
def string_printer(n: int) -> bool:
    """
    :type n: int
    :rtype: List[str]
    """
    # ans list
    ans = []

    for num in range(1,n+1):

        divisible_by_3 = (num % 3 == 0)
        divisible_by_2 = (num % 2 == 0)

        if divisible_by_3 and divisible_by_2:
            # Divides by both 3 and 2, add FizzBuzz
            ans.append("Mind Hunters")
        elif divisible_by_3:
            # Divides by 3, add Fizz
            ans.append("The Mentalist")
        elif divisible_by_2:
            # Divides by 2, add Buzz
            ans.append("Dexter")
        else:
            # Not divisible by 3 or 2, add the number
            ans.append(str(num))

    return ans
```

#### Output

```shell
string_printer(10)

['1',
 'Dexter',
 'The Mentalist',
 'Dexter',
 '5',
 'Mind Hunters',
 '7',
 'Dexter',
 'The Mentalist',
 'Dexter']

```

## Question 3: First Unique Character in a String
Given a string, find the first non-repeating character in it and return it's index. If it doesn't exist, return -1.

#### Method 1:

```python3

class Solution:
    def firstUniqChar(self, s: str) -> int:
        for a in s:
            if s.count(a) == 1:
                return s.find(a)
                break

        return -1

```

#### Method 2:

```python3

class Solution:
    def firstUniqChar(self, s: str) -> int:
        letters = [letter for letter in s]

        repeated, new = [], set()

        for letter in letters:

            if letter in repeated:
                new.add(letter)

            repeated.append(letter)

        list1 = [ele for ele in repeated if ele not in new] 
        try:
            return s.find(list1[0])
        except:
            return -1

```

### Output

```shell

string = 'loveleetcode'

unique_character = Solution()
unique_character.firstUniqChar(string)

```
