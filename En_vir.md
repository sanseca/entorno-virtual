from flask import Flask
import random

app = Flask(__name__)

@app.route("/")
def hello_world():
    return '<h1>Hola en <a>http://127.0.0.1:5000/datos</a>, podras encontrar algunos datos interesantes y en <a>http://127.0.0.1:5000/lanzamiento_moneda</a>, podras lanzar una moneda</h1>'

@app.route("/lanzamiento_moneda")
def lanzamiento():
    moneda = ["cara","cruz"]
    return f'<h2>En esta pagina puedes lanzar una moneda (recarga la pagina para que otra vez se lanze la moneda) Te toco: {random.choice(moneda)}</h2>'
    
    
@app.route("/datos")
def datosInteresantes():
    datos = ["La mayoría de las personas que sufren adicción tecnológica experimentan un fuerte estrés cuando se encuentran fuera del área de cobertura de la red o no pueden utilizar sus dispositivos",
    "Según un estudio realizado en 2018, más del 50% de las personas de entre 18 y 34 años se consideran dependientes de sus smartphones"]
    return f'<h3>{random.choice(datos)}</h3>'

app.run(debug=True)
