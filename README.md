# JavaScript--Vasya-Clerk
/*The new "Avengers" movie has just been released!
 There are a lot of people at the cinema box office
 standing in a huge line. Each of them has a single 10
0, 50 or 25 dollar bill. An "Avengers" ticket costs 
25 dollars. Vasya is currently working as a clerk.
 He wants to sell a ticket to every single person
 in this line.

Can Vasya sell a ticket to every person and give 
change if he initially has no money and sells the 
tickets strictly in the order people queue?

Return YES, if Vasya can sell a ticket to every
 person and give change with the bills he has at 
hand at that moment. Otherwise return NO.*/

function tickets(peopleInLine){
let amount25 = 0;
let amount50 = 0;
let amount100 = 0;
for(let i = 0; i < peopleInLine.length; i++){
if(peopleInLine[i] === 100){
if(amount25 >= 3){
amount25 -= 3;
amount100++;
}
else if(amount25 >= 1 && amount50 >= 1){
amount25 -= 1;
amount50 -= 1;
amount100++;
}else{
return "NO";
}
}
if(peopleInLine[i] === 50){
if(amount25 >= 1){
amount25--;
amount50++;
}else {
return "NO";
}
}
if(peopleInLine[i] === 25){
amount25++;
}
}
return "YES";
} 
