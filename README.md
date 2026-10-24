# thr
my first site
from flask import Flask, render_template_string

app = Flask(__name__)

# Простой HTML-код страницы прямо внутри Python
HTML_PAGE = """
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Мой первый сайт на Python</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .card {
            background: rgba(255, 255, 255, 0.1);
            padding: 40px;
            border-radius: 15px;
            backdrop-filter: blur(10px);
            text-align: center;
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
        }
        h1 { margin-bottom: 10px; font-size: 2.5rem; }
        p { font-size: 1.2rem; opacity: 0.9; }
    </style>
</head>
<body>
    <div class="card">
        <h1>Привет, мир! 🚀</h1>
        <p>Мой сайт на Python успешно работает в интернете!</p>
    </div>
</body>
</html>
"""


@app.route("/")
def home():
    return render_template_string(HTML_PAGE)


if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
