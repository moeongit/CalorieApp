# Foodie

Foodie is a web application that helps you find the nutritional values and calories in your food. It also provides information on how to burn those calories through various activities.

## Features

- Search for nutritional values of food items.
- View detailed nutritional information including carbohydrates, cholesterol, fats, fiber, potassium, protein, sodium, and sugar.
- Get recommendations on how to burn the calories through different physical activities.
- Alerts for high sodium and high sugar content in foods.

## Screenshot

![image](https://github.com/moeongit/CalorieApp/assets/111477874/f55c2bc8-4530-42e8-945d-a597c244484e)



## Installation

### Prerequisites

- Python 3.x
- Django
- PostgreSQL (or another preferred database)
- Node.js and npm (if you use React or other Node.js tools)

### Setup

1. Clone the repository:

    ```sh
    git clone https://github.com/yourusername/foodie.git
    cd foodie
    ```

2. Create a virtual environment and activate it:

    ```sh
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the dependencies:

    ```sh
    pip install -r requirements.txt
    ```

4. Set up the database:

    ```sh
    sudo -i -u postgres
    psql
    CREATE DATABASE foodie;
    CREATE USER foodie_user WITH PASSWORD 'yourpassword';
    ALTER ROLE foodie_user SET client_encoding TO 'utf8';
    ALTER ROLE foodie_user SET default_transaction_isolation TO 'read committed';
    ALTER ROLE foodie_user SET timezone TO 'UTC';
    GRANT ALL PRIVILEGES ON DATABASE foodie TO foodie_user;
    \q
    exit
    ```

5. Configure the database in `settings.py`:

    ```python
    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.postgresql',
            'NAME': 'foodie',
            'USER': 'foodie_user',
            'PASSWORD': 'yourpassword',
            'HOST': 'localhost',
            'PORT': '',
        }
    }
    ```

6. Run migrations and start the development server:

    ```sh
    python manage.py migrate
    python manage.py createsuperuser  # Create a superuser for admin access
    python manage.py runserver
    ```

7. Open your browser and go to `http://127.0.0.1:8000/` to see the application.

## Usage

1. Enter a food item in the search bar and click "Find calories."
2. View the nutritional values and calorie-burning recommendations.
3. Check for alerts on high sodium and high sugar content.

## Contributing

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-foo`).
3. Make your changes.
4. Commit your changes (`git commit -am 'Add some foo'`).
5. Push to the branch (`git push origin feature-foo`).
6. Create a new Pull Request.
