# Day 4 -  Reverse Integer #

  From: Leetcode

  Difficulty: Easy
  
## Description of the problem ##
 
    Given a 32-bit signed integer, reverse digits of an integer.

    Note:
    Assume we are dealing with an environment that could only store integers within the 32-bit signed integer range: [−2^31,  2^31 − 1]. 
    For the purpose of this problem, assume that your function returns 0 when the reversed integer overflows.
    
## Example 1: ##
    
    Input: x = 123
    Output: 321
    
## Example 2: ##

    Input: x = -123
    Output: -321
    
## Example 3: ##
  
    Input: x = 120
    Output: 21
    
## Example 4: ##

    Input: x = 0
    Output: 0
    
## Constraints: ##

    -2^31 <= x <= 2^31 - 1
    
## Core of thought ##

    I don't think it is difficult. The most important thing here is how to use less memory and cost less time. I am not so familiar with this part so if you have some 
    comments of suggestions, please tell me.
    
## My code ##

    class Solution(object):
      def reverse(self,x):
          """
          :type x: int
          :rtype: int
          """
          if x >= 0:
              signal = ''
          else:
              signal = '-'
          str_of_x = str(abs(x))
          list_x = list(str_of_x)
          list_x.reverse()
          lens_of_x = len(str_of_x)
          is_first_zero = 0
          str_result = []
          if x == 0:
              return 0
          else:
              for i in range(len(list_x)):
                  if is_first_zero == 1:
                      str_result.append(list_x[i])
                  else :
                      if list_x[i] != '0':
                          is_first_zero = 1
                          str_result.append(list_x[i])

          string_result = ''.join(str_result)
          string_result = signal + string_result
          int_result = int(string_result)
          if int_result > (2**31-1):
              int_result = 0
          elif int_result <(-2**31):
              int_result = 0
          return int_result
          
      ## A not bad result I choosed ##
      
          Runtime: 16 ms, faster than 88.71% of Python online submissions for Reverse Integer.
          Memory Usage: 13.3 MB, less than 89.90% of Python online submissions for Reverse Integer.
