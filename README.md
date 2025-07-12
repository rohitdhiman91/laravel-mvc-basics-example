# 🚀 Laravel MVC Basics – Beginner-Friendly Example

This is a simple Laravel project that demonstrates the **Model-View-Controller (MVC)** architecture using a basic User Profile Viewer.

🎯 Perfect for Laravel beginners who want to understand:
- How Models, Views, and Controllers work together
- Basic routing and Blade templating
- Using Eloquent ORM to fetch data

---

## 📁 Project Structure

```

app/
├── Http/
│   └── Controllers/
│       └── UserController.php
├── Models/
│   └── User.php
resources/
└── views/
└── users/
├── index.blade.php
└── show\.blade.php
routes/
└── web.php
database/
└── seeders/
└── DatabaseSeeder.php

````

---

## 🧠 What You’ll Learn

- MVC structure in Laravel
- Eloquent ORM usage
- Blade template basics
- Laravel route-to-view flow

---

## 🛠️ Getting Started

### 1. Clone the Repo
```bash
git clone https://github.com/rohitdhiman91/laravel-mvc-basics-example.git
cd laravel-mvc-basics-example
````

### 2. Install Dependencies

```bash
composer install
```

### 3. Setup Environment

```bash
cp .env.example .env
php artisan key:generate
```

### 4. Configure Database

Update your `.env` file with your database credentials, then run:

```bash
php artisan migrate --seed
```

### 5. Serve the App

```bash
php artisan serve
```

Visit `http://127.0.0.1:8000/users` in your browser.

---

## 🔎 MVC Breakdown

### 🔹 Model – `User.php`

```php
$user = User::where('email', $email)->first();
```

### 🔹 View – `index.blade.php` & `show.blade.php`

```blade
<!-- index.blade.php -->
<h1>All Users</h1>
<ul>
  @foreach ($users as $user)
    <li><a href="{{ route('users.show', $user->id) }}">{{ $user->name }}</a></li>
  @endforeach
</ul>
```

```blade
<!-- show.blade.php -->
<h1>{{ $user->name }}</h1>
<p>Email: {{ $user->email }}</p>
<a href="{{ route('users.index') }}">← Back to list</a>
```

### 🔹 Controller – `UserController.php`

```php
public function index() {
    $users = User::all();
    return view('users.index', compact('users'));
}

public function show($id) {
    $user = User::findOrFail($id);
    return view('users.show', compact('user'));
}
```

---

## 🧪 Dummy Data

The included seeder generates 10 random users (if you have Laravel factories set up).
Make sure your database is ready, then run:

```bash
php artisan migrate --seed
```

---

## 📚 Learn More

This project is designed to help beginners *see* Laravel’s MVC pattern in action.

🔗 Want a video tutorial, article, or carousel version of this? Check the link in the bio or my dev profiles!

---

## 🤝 Contribute

Feel free to fork, star, or extend this repo! Pull requests are welcome for:

* Adding Create/Update/Delete features
* REST API version
* Comments or authentication

---

## 📩 Stay Connected

Follow me for beginner-friendly Laravel content on:

* GitHub: [@rohitdhiman91](https://github.com/rohitdhiman91)
* Substack: https://rohitdhiman91.substack.com
* Instagram: [@rohitdhiman91](https://instagram.com/rohitdhiman91)

---

## 🏷️ Tags

`#Laravel` `#PHP` `#MVC` `#WebDevelopment` `#Blade` `#Eloquent` `#LaravelForBeginners`

```
