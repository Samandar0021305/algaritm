# algaritm
solution 1 
Write a function that when given a URL as a string, parses out just the domain name and returns it as a string. For example:

function domainName(url){
  url = url.replace("https://", '');
  url = url.replace("http://", '');
  url = url.replace("www.", '');
  return url.split('.')[0];
}

solition  2 
Your task is to sort a given string. Each word in the string will contain a single number. This number is the position the word should have in the result.

Note: Numbers can be from 1 to 9. So 1 will be the first word (not 0).

If the input string is empty, return an empty string. The words in the input String will only contain valid consecutive numbers.

function order(words){
 if(words == ""){
    return ""
  }else{
     
    let array = words.split(" ")
    
    function filtred(str){
  let array =  str.split("")
   for(let item of array){
       if(item / 1 == item){
           array[0] = item
       }
   }
   return array
}
     for(let i=0;i<array.length;i++){
        for(let j=0;j<array.length -i-1;j++){
            if(parseInt(filtred(array[j])) > parseInt(filtred(array[j+1]))){
                let temp = array[j]
                array[j] = array[j+1]
                array[j+1] = temp
            }
        }
     }
     return array.join(" ")
  }
}


solution 3 

Looks like some hoodlum plumber and his brother has been running around and damaging your stages again.

The pipes connecting your level's stages together need to be fixed before you receive any more complaints.

Pipes list is correct when each pipe after the first index is greater (+1) than the previous one, and that there is no duplicates.

Task
Given the a list of numbers, return a fixed list so that the values increment by 1 for each index from the minimum value up to the maximum value (both included).

function pipeFix(numbers){
  let k = []
  for(let i= numbers[0];
  i<=numbers[numbers.length - 1];i++){
    k.push(i)
  }
  return k
}

solution 4 

Digital root is the recursive sum of all the digits in a number.

Given n, take the sum of the digits of n. If that value has more than one digit, continue reducing in this way until a single-digit number is produced. The input will be a non-negative integer.


function digitalRoot(n) {
 if(n <10){
    return n
  }else{
      
      let array = n.toString().split("")
     while(array.length  > 1){
       let summa = array.reduce((a,b)=>{
          return Number(a) + Number(b)
      })  
      array= summa.toString().split("")
     }
   
     
     return Number(array.join(""))
  }
}

solution 5 

Kids drink toddy.
Teens drink coke.
Young adults drink beer.
Adults drink whisky.
Make a function that receive age, and return what they drink.

Rules:

Children under 14 old.
Teens under 18 old.
Young under 21 old.
Adults have 21 or more.


function peopleWithAgeDrink(old) {
 if(old >= 21){
   return "drink whisky"
 }else if(old < 21 && old >= 18){
return "drink beer"
 }else if(old < 18 && old >= 14){
   return "drink coke" 
 }else if(old<=14){
   return "drink toddy"
 }
};

solution 6

The first input array is the key to the correct answers to an exam, like ["a", "a", "b", "d"]. The second one contains a student's submitted answers.

The two arrays are not empty and are the same length. Return the score for this array of answers, giving +4 for each correct answer, -1 for each incorrect answer, and +0 for each blank answer, represented as an empty string (in C the space character is used).

If the score < 0, return 0.


function checkExam(array1, array2) {
 let j = 0
  for(let i =0;i<array1.length;i++){
   if(array1[i] == array2[i] && i ==i){
      j+=4
   }else if(array2[i] ==""){
     j +=0
   }
    else{
     j-=1
   }
 }
  if(j < 0){
    return 0
  }
  
  return j
}

solution 7 
Messi is a soccer player with goals in three leagues:

LaLiga
Copa del Rey
Champions
Complete the function to return his total number of goals in all three leagues.

Note: the input will always be valid.

For example:

function goals (laLigaGoals, copaDelReyGoals, championsLeagueGoals) {
  return laLigaGoals + copaDelReyGoals + championsLeagueGoals
}



solution 8
You will be given an array and a limit value. You must check that all values in the array are below or equal to the limit value. If they are, return true. Else, return false.

You can assume all values in the array are numbers.


function smallEnough(a, limit){
let numbers = a[0]
for(let item of a){
  if(numbers < item){
    numbers = item
  }
}
  
  if(numbers == limit || limit > numbers){
    return true 
  }else{
    return false
  }
}


solution 9
instructions
Write a function that takes a single string (word) as argument. The function must return an ordered list containing the indexes of all capital letters in the string.

Example
var capitals = function (word) {
   let user = word.toLowerCase()
   let one = word.split("");
   let two = user.split("");
  let m = []
   for(let i =0; i<one.length;i++){
     if(one[i] != two[i]){
      m.push(i) 
     }
   }
  return m
  
};



solution 10 


Write a function to convert a name into initials. This kata strictly takes two words with one space in between them.

The output should be two capital letters with a dot separating them.

It should look like this:


function abbrevName(name){
let array = name.split(" ")
let one = array[0].split("")
let two = array[1].split("")
return `${one[0].toUpperCase()}.${two[0].toUpperCase()}`
}


solution 11

Write a function that takes an array of numbers (integers for the tests) and a target number. It should find two different items in the array that, when added together, give the target value. The indices of these items should then be returned in a tuple / list (depending on your language) like so: (index1, index2).

For the purposes of this kata, some tests may have multiple answers; any valid solutions will be accepted.

The input will always be valid (numbers will be an array of length 2 or greater, and all of the items will be numbers; target will always be the sum of two different items from that array).

Based on: http://oj.leetcode.com/problems/two-sum/


function twoSum(numbers, target) {
  for(let  i =0;i<numbers.length;i++){
    for(let j =0;j<numbers.length;j++){
      if(numbers[i] + numbers[j] == target && i!=j){
        return [i,j]
      }
    }
  }
}



solution 12

If you can't sleep, just count sheep!!

Task:
Given a non-negative integer, 3 for example, return a string with a murmur: "1 sheep...2 sheep...3 sheep...". Input will always be valid, i.e. no negative integers.

var countSheep = function (num){
if(num == 0){
  return ""
} else{
  let str = '1 sheep...'
  for(let i = 2; i<=num;i++){
    str +=`${i} sheep...`
  }
  return str
}
}


solution 13
Given an array of integers.

Return an array, where the first element is the count of positives numbers and the second element is sum of negative numbers. 0 is neither positive nor negative.

If the input is an empty array or is null, return an empty array.

Example
For input [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, -11, -12, -13, -14, -15], you should return [10, -65].


function countPositivesSumNegatives(input) {
  if(input == null ){
    return []
  }else if(input.length == 0){
    return []
  }else{
     let arrayOne = []
     let arrayTwo = []
     for(let item of input){
       if(item > 0){
         arrayOne.push(item)
       }else if(item < 0){
         arrayTwo.push(item)
       }
     }
    let summa = 0
    for(let index of arrayTwo){
summa +=index;
    }  
    return [arrayOne.length,summa]
  }  
}


solution 14 

Given an array of integers, return a new array with each value doubled.

For example:

[1, 2, 3] --> [2, 4, 6]



function maps(x){
 let k = []
  for(let item of x){
   k.push(item*2)
   
 }
  return k
  
}

solution 15 

You are given an odd-length array of integers, in which all of them are the same, except for one single number.

Complete the method which accepts such an array, and returns that single different number.

The input array will always be valid! (odd-length >= 3)


function stray(numbers) {
  let m = []
let f = numbers[0]
  for(let i = 0; i<numbers.length; i++){
   if(numbers[0] != numbers[i] ){
     m.push(numbers[i])
   }
  } 

   if(m.length >= 2){
  return f
   }else{
    return m[0]
   }
  
  
}


solution 16

Your classmates asked you to copy some paperwork for them. You know that there are 'n' classmates and the paperwork has 'm' pages.

Your task is to calculate how many blank pages do you need. If n < 0 or m < 0 return 0.


function paperwork(n, m) {
 if(n <= 0 || m <=0 ){
   return 0
 } else{
   return n*m
 }
}


solution 17

You probably know the "like" system from Facebook and other pages. People can "like" blog posts, pictures or other items. We want to create the text that should be displayed next to such an item.

Implement the function which takes an array containing the names of people that like an item. It must return the display text as shown in the examples:


function likes(names) {
  if(names.length == 0){
    return 'no one likes this'
  }else if(names.length == 1){
  return `${names[0]} likes this`
  }else if(names.length == 2){
    return `${names[0]} and ${names[1]} like this`
  }else if(names.length == 3){
  return `${names[0]}, ${names[1]} and ${names[2]} like this`
  }else if(names.length >= 4){
    let k = names.length - 2;
    return `${names[0]}, ${names[1]} and ${k} others like this`
  }
}

solution 18

Create a function which answers the question "Are you playing banjo?".
If your name starts with the letter "R" or lower case "r", you are playing banjo!

The function takes a name as its only argument, and returns one of the following strings:

function areYouPlayingBanjo(name) {
   let array = name.split("")
   if(array[0].toLowerCase() == 'r'){
return `${name} plays banjo`
   }else{
 return `${name} does not play banjo`
   }

}



solution 19

Create a function called _if which takes 3 arguments: a boolean value bool and 2 functions (which do not take any parameters): func1 and func2

When bool is truth-ish, func1 should be called, otherwise call the func2.

function _if(bool, func1, func2) { 
  if(bool){
    return  func1(true)
  }else{
  return func2(false)
  }
}




solution 20
iven a list of integers, determine whether the sum of its elements is odd or even.

Give your answer as a string matching "odd" or "even".

If the input array is empty consider it as: [0] (array with a zero).

Examples:

function oddOrEven(array) {
   //enter code here
  let sum = 0
   for(let item of array){
     sum +=item
   }
   if(sum % 2 ==0 ){
     return 'even'
   }else if(sum % 2 !==0){
     return 'odd'
   }else if(array.length == 0){
     return 'even'
   }else if(sum == 0){
    return 'even'
   }
}

solution 21

This function should test if the factor is a factor of base.

Return true if it is a factor or false if it is not.

About factors
Factors are numbers you can multiply together to get another number.

2 and 3 are factors of 6 because: 2 * 3 = 6

You can find a factor by dividing numbers. If the remainder is 0 then the number is a factor.
You can use the mod operator (%) in most languages to check for a remainder
For example 2 is not a factor of 7 because: 7 % 2 = 1

Note: base is a non-negative number, factor is a positive number.


function checkForFactor (base, factor) {
  // code here
  if(base % factor == 0){
    return true
  }else{
    return false
  }
}


solution 22

Given two integers a and b, which can be positive or negative, find the sum of all the integers between and including them and return it. If the two numbers are equal return a or b.

Note: a and b are not ordered!

Examples (a, b) --> output (explanation)

function getSum( a,b )
{
   if(a == b){
     return a
   }else if(b > a){
     let sum = 0;
     for(let i = a ; i <= b;i++){
       sum+=i;
     }
     return sum
   }else if(a>b){
      let sum = 0;
     for(let i = b ; i <= a;i++){
       sum+=i;
     }
     return sum
   }
}



solution 23


In this kata you will create a function that takes a list of non-negative integers and strings and returns a new list with the strings filtered out.

function filter_list(l) {
  // Return a new array with the strings filtered out
 let results = []
    for(let item of l){
       if(typeof item === 'number'){
         results.push(item)
       }
    }
    return results
}



solution 24
Complete the solution so that the function will break up camel casing, using a space between words.

// complete the function
function solution(string) {
   let arry = string.split("")
     let newArry = []
     for(let item of arry){
        if(item.toUpperCase() == item){
          newArry.push(" ", item)
        }else{
            newArry.push(item)
        }
     }
    return newArry.join("")
}


