# First-Year-CTSD-Project
/* Write a C program that takes two strings as input and checks whether  
two strings are anagrams. */ 
#include <stdio.h> 
#include <string.h> 
int findanagram(char str1[], char str2[]) 
{ 
 int num1[26]={0},num2[26]={0},i=0; 
 // check's length same or not 
 if(strlen(str1)!=strlen(str2)) 
  return 0; 
    //find Frequency of str1 
 for(i=0;str1[i]!='\0';i++) 
 { 
  if(str1[i]>='a'&&str1[i]<='z') 
  { 
   num1[str1[i]-97]++; 
  } 
  if(str1[i]>='A'&&str1[i]<='Z') 
  { 
   num1[str1[i]-65]++; 
  }  
 } 
 //find Frequency of str2  
    for(i=0;str2[i]!='\0';i++) 
 
 { 
  if(str2[i]>='a'&&str2[i]<='z') 
  { 
   num2[str2[i]-97]++; 
  } 
  if(str2[i]>='A'&&str2[i]<='Z') 
  { 
   num2[str2[i]-65]++; 
  }  
 } 
 // check's Frequency is equal or not   
    for(i=0;i<26;i++) 
    { 
        if(num1[i] != num2[i]) 
            return 0; 
    } 
    return 1; 
} 
int main() 
{ 
    char str1[100],str2[100]; 
    int flag;  
    printf("Enter the string\n"); 
    gets(str1); 
    printf("Enter another string\n"); 
    gets(str2); 
    flag = findanagram(str1,str2); 
 
    if (flag == 1) 
        printf("%s and %s are anagrams.\n",str1,str2); 
    else 
        printf("%s and %s are not anagrams.\n",str1,str2); 
    return 0; 
}
