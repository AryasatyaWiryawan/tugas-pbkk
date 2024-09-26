# PBKK - D - Project Laravel
- NRP : 5025221256
- Name : Aryasatya Wiryawan

## Table Of Contents
- [Installation](#installation)
- [UI](#ui)
- [Question](#answer-question)
## Installation
1. Git clone project :
```cmd
git clone https://github.com/AryasatyaWiryawan/tugas-pbkk.git
```
2. Navigate to project folder :

```cmd
cd tugas-pbkk
```
3. Install Composer :
```cmd
composer install
```
4. Install NPM Dependencies :
```cmd
npm install

npm install -D tailwindcss postcss autoprefixer
```
5. Set Up the .env File :
```cmd
cp .env.example .env
```
6. Generate Application Key :
```cmd
php artisan key:generate
```
7. Set up database :
```cmd
php artisan migrate
```
8. Serve Application :
```cmd
php artisan serve
```

## UI

Home view:
![image](https://github.com/user-attachments/assets/37a84db2-3174-4b1a-b3fb-4bf356d238c0)

Post :
![image](https://github.com/user-attachments/assets/b6aee052-9a9a-4c63-aab7-4c7ae83f1bef)

## Answer Question
`Which one is better between using *Eloquent ORM* or *Query Builder*?`

The choice between using *Eloquent ORM* and *Query Builder* in Laravel depends on the specific use case and project requirements. Here’s an objective comparison:

### 1. *Eloquent ORM*

#### Pros:
- *Object-Oriented Approach*: Eloquent uses an Active Record pattern, allowing you to interact with your database using models and object-oriented syntax. This makes it easier for developers familiar with OOP concepts.
- *Readable Syntax*: Eloquent’s syntax is highly readable and concise, making code easier to write and maintain.
  php
  $user = User::where('email', 'example@example.com')->first();
  
- *Relationships Handling*: Eloquent provides built-in support for defining relationships between models (one-to-many, many-to-many, etc.), simplifying complex queries.
- *Automatic Timestamps & Soft Deletes*: Eloquent automatically manages created_at and updated_at timestamps, and also has built-in soft delete functionality.
- *Mutators & Accessors*: Eloquent allows you to modify data when it is retrieved from or written to the database using mutators and accessors.

#### Cons:
- *Performance*: Eloquent is relatively slower than Query Builder when handling large datasets because it retrieves entire models (including relationships) into memory.
- *Overhead*: For simple queries, Eloquent might introduce unnecessary overhead as it loads models and relationships.
- *Less Control*: Eloquent abstracts much of the SQL logic, which can make it harder to write more complex or optimized queries compared to Query Builder.

### 2. *Query Builder*

#### Pros:
- *Faster & Lightweight*: Query Builder is faster and uses less memory since it directly interacts with the database, focusing solely on the query, not the model’s features.
  php
  $users = DB::table('users')->where('email', 'example@example.com')->first();
  
- *Better for Complex Queries*: It gives you more control over raw SQL queries, allowing you to write highly optimized and complex queries.
- *Flexibility*: You can use Query Builder to execute raw SQL when needed, giving you complete control over the query structure.
- *Fine-grained control*: It offers more precise control for cases where specific SQL features are needed, such as joins or subqueries, without the overhead of ORM.

#### Cons:
- *Less Readable*: While Query Builder is still relatively easy to read, it requires more verbose code compared to Eloquent.
- *Manual Relationship Handling*: Query Builder doesn’t have built-in relationship handling like Eloquent. You’ll need to manually join tables and handle foreign key relationships.
- *No Object-Oriented Benefits*: Query Builder works directly with arrays, meaning you lose out on the OOP benefits of Eloquent, such as methods, relationships, and accessors.

### Objective Summary:

- *Use Eloquent* if you prefer object-oriented programming, need easy relationship handling, and want readable, maintainable code with built-in features like timestamps and soft deletes. Eloquent is ideal for small to medium-sized projects with straightforward data interactions.
  
- *Use Query Builder* if you prioritize performance, need precise control over complex queries, or are working with large datasets where the overhead of loading models is a concern. Query Builder is also a better choice when you need to optimize complex queries for performance or when you need fine-tuned control over the generated SQL.

In conclusion, *Eloquent ORM* is great for developer productivity and ease of use, while *Query Builder* excels in performance and flexibility for complex scenarios. Depending on your needs, you might even use a combination of both in a single project.


