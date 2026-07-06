# Flask-5
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
