# Project Overview – Dube Café Ordering Chatbot


## Introduction to Amazon Lex

Amazon Lex is an AWS service that enables developers to build conversational interfaces such as chatbots and virtual assistants. It uses natural language understanding and automatic speech recognition, which are the same technologies that power Amazon Alexa. With Lex, we can design bots that understand text or speech, capture data from customers, and respond intelligently.

## Amazon Lex core capabilities

The core capabilities of Amazon Lex include creating intents to define what the user wants, utterances to capture the different ways customers may ask for something, and slots to collect structured information such as a name, a drink type, or a size. Lex also provides branching logic and responses to guide the user through different paths in a conversation.


## Overview
This project focuses on designing and building a chatbot for Dube Café using Amazon Lex. The chatbot will provide customers with a convenient way to place coffee and pastry orders online, reducing the challenges the café faces with missed phone calls, order errors, and long queues.

## Problem Statement

Dube Café is a growing coffee shop in Johannesburg that is facing several challenges as its customer base expands. During peak hours, staff often miss phone calls, which leads to lost orders. When calls are answered, background noise or rushed conversations frequently result in order errors. Long queues inside the café also frustrate customers who want a quick and simple purchase. In addition, the café currently offers only in-store and phone ordering, limiting customer convenience.

## Client Requirement

To solve these challenges, Dube Café requires a chatbot to be integrated into their website. The chatbot should allow customers to place coffee and pastry orders online and personalize the experience by asking for the customer’s name. It must also provide structured menu options such as drinks, milk choices, croissants, extras, and sizes. Furthermore, the chatbot should confirm each order to avoid mistakes and remain available 24/7, even outside of store operating hours.

## Solution Overview

We developed a chatbot using Amazon Lex to streamline the online ordering process. The bot begins by capturing the customer’s name so it can respond personally, for example: “Nice to meet you, Alex! What would you like to order today?” Customers can then select from menu-based options including coffee, cappuccino, tea, or iced tea. The chatbot guides them through customization choices such as milk type, caffeine preference, size, and whether they would like an extra shot of espresso. It also cross-sells pastries by offering croissants in plain, chocolate, or cheese flavours. Finally, the bot confirms the full order and thanks the customer.

This solution creates a smooth and interactive flow that feels like speaking to a barista, while reducing staff workload and improving customer satisfaction.

## Technical Approach

Following AWS Lex Bot Creation Project Part 1 & 2 steps:

### 1. Create Bot

Bot name: DubeCafe

Language: English (ZA)

### 2. Create Intent

Intent name: Order

Sample utterances:

I want to order

Order coffee

Place an order

Hi

Start order


![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/a87d897672f8e5ed5746340517d37ae6dd397587/Project%3A%20Amazon%20Lex%20Bot/utterances.png)

### 3. Create Slots

We added slots to capture order details:

NameSlot → customer’s name (personal touch).

DrinkType → Coffee, Tea, Cappuccino, Iced Tea.

Caff → Caffeinated or Decaffeinated (for tea orders).

MilkType → Almond, Low-fat, Full-cream.

Size → Small, Regular, Large.

ExtraShot → Yes or No.

Croissant → Yes or No.

CroissantType → Plain, Chocolate, Cheese.

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/a87d897672f8e5ed5746340517d37ae6dd397587/Project%3A%20Amazon%20Lex%20Bot/slot%20type%20for%20drinktype.png)


![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/a87d897672f8e5ed5746340517d37ae6dd397587/Project%3A%20Amazon%20Lex%20Bot/slottype%20for%20size.png)

### 4. Conditional Branching

If DrinkType = Coffee / Cappuccino / Iced Coffee → Elicit ExtraShot.

If DrinkType = Tea → Skip ExtraShot, elicit Caff.

If Croissant = Yes → Elicit CroissantType.

If Croissant = No → Move to order confirmation.

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/a87d897672f8e5ed5746340517d37ae6dd397587/Project%3A%20Amazon%20Lex%20Bot/condtion%20branch.png)


![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/a87d897672f8e5ed5746340517d37ae6dd397587/Project%3A%20Amazon%20Lex%20Bot/tea%20branch.png)

### 5. Challenges

One of the main challenges I faced while creating the bot was with conditional branching. At first, I tried adding it under the initial response, but I struggled to move smoothly to the next question in the conversation flow. After doing some research, I discovered that using slots and slot types was a much easier and more effective way to achieve the desired flow. Once I applied this approach, the bot worked as expected.

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/46acde4870f33d249f107f0a24f548652e3f2883/Project%3A%20Amazon%20Lex%20Bot/error.png)

### 6. Order Flow (Questions)

“Hi there! First of all, what’s your name?”

“Nice to meet you, {YourName}. What drink would you like? Coffee, Cappuccino, Tea, or Iced Tea?”

If coffee-based: “Would you like an extra shot of espresso? Yes or No?”

If tea: “Would you like it caffeinated or decaffeinated?”

“What type of milk would you like? Almond, Low-fat, or Full-cream?”

“What size would you like? Small, Regular, or Large?”

“Would you like your {DrinkType} to come with a croissant? Yes or No?”

If Yes: “Which flavour of croissant would you like: Plain, Chocolate, or Cheese?”

Bot confirms: “Great,{YourName}! Your order is a {Size} {DrinkType} with {MilkType} milk {+ extra shot if chosen} and a {CroissantType if selected}. Thank you for ordering from Dube Café!”

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/fc05452a52644bdd5721860b684057329fc183ed/Project%3A%20Amazon%20Lex%20Bot/Screenshot%202025-09-04%20045717.png)


![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/fc05452a52644bdd5721860b684057329fc183ed/Project%3A%20Amazon%20Lex%20Bot/Screenshot%202025-09-04%20045754.png)


![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/fc05452a52644bdd5721860b684057329fc183ed/Project%3A%20Amazon%20Lex%20Bot/Screenshot%202025-09-04%20045829.png)

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/fc05452a52644bdd5721860b684057329fc183ed/Project%3A%20Amazon%20Lex%20Bot/Screenshot%202025-09-04%20045853.png)

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/fc05452a52644bdd5721860b684057329fc183ed/Project%3A%20Amazon%20Lex%20Bot/Screenshot%202025-09-04%20045910.png)

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/fc05452a52644bdd5721860b684057329fc183ed/Project%3A%20Amazon%20Lex%20Bot/Screenshot%202025-09-04%20045938.png)

### 7. Conclusion

By building the Dube Café Ordering Chatbot with Amazon Lex, we solved key business challenges such as missed phone orders, order errors, and long wait times. The chatbot provides customers with a personalized, reliable, and engaging way to place their orders, while freeing up staff to focus on preparation and service.



