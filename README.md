import os
from flask import Flask, render_template, request

BAZA_JILD = os.path.dirname(os.path.abspath(__file__))
templates_path = os.path.join(BAZA_JILD, 'templates')
static_path = os.path.join(BAZA_JILD, 'static')

app = Flask(__name__, template_folder=templates_path, static_folder=static_path)

MAHSULOTLAR = [
    "Smartfon iPhone 15 Pro",
    "Noutbuk ASUS ZenBook",
    "Mexanik klaviatura A4 Bloody",
    "Simsiz sichqoncha Rapoo VT9PRO",
    "Monitor Samsung Odyssey G5",
    "Geymerlar uchun quloqchin (Headset)",
    "Smart soat Apple Watch Series 9"
]
if __name__ == '__main__':
    app.run(debug=True)

    <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <link rel="stylesheet" href="../Flask%205.py">
<link rel="stylesheet" href="{{ url_for('static', filename='style.css') }}"></head>
<body>
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Qidiruv Tizimi</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='style.css') }}">
</head>
<body>

    <div class="search-container">
        <h2>Kutubxona Qidiruv Tizimi</h2>

        <form action="/" method="GET" class="search-form">
            <input
                type="text"
                name="q"
                placeholder="Qidiruv so'zini kiriting..."
                value="{{ qidiruv_matni }}"
                required
            >
            <button type="submit">Qidirish</button>
        </form>

        <hr>

        <div class="results-container">
            {% if qidiruv_matni %}
                <h3>"{{ qidiruv_matni }}" bo'yicha qidiruv natijalari:</h3>

                {% if natijalar %}
                    <ul class="results-list">
                        {% for natija in natijalar %}
                            <li>{{ natija }}</li>
                        {% endfor %}
                    </ul>
                {% else %}
                    <p class="no-result">Hech narsa topilmadi</p>
                {% endif %}
            {% endif %}
        </div>
    </div>

</body>
</html>
</body>
</html>

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #f4f7f6;
    color: #333;
    padding: 40px;
    display: flex;
    justify-content: center;
}

.search-container {
    background: #ffffff;
    padding: 30px;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0,0,0,0.1);
    width: 100%;
    max-width: 500px;
}

h2 {
    text-align: center;
    color: #2c3e50;
    margin-bottom: 20px;
}

.search-form {
    display: flex;
    gap: 10px;
}

.search-form input {
    flex: 1;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-size: 16px;
}

.search-form button {
    padding: 10px 20px;
    background-color: #3498db;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 16px;
    transition: background 0.2s;
}

.search-form button:hover {
    background-color: #2980b9;
}

hr {
    margin: 20px 0;
    border: 0;
    border-top: 1px solid #eee;
}

.results-list {
    list-style: none;
    padding: 0;
}

.results-list li {
    padding: 10px;
    background: #f9f9f9;
    border-left: 4px solid #3498db;
    margin-bottom: 8px;
    border-radius: 0 4px 4px 0;
}

.no-result {
    color: #e74c3c;
    font-weight: bold;
    text-align: center;
    padding: 10px;
    background: #fadbd8;
    border-radius: 4px;
}
