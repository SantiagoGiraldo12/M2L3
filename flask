from flask import Flask
import random

app = Flask(__name__)
nombre = "Santiago Giraldo"
facts_list = ["Elon Musk afirma que las redes sociales están diseñadas para mantenernos dentro de la plataforma, de modo que pasemos el mayor tiempo p",
    "Según un estudio realizado en 2018, más del 50(%) de las personas de entre 18 y 34 años se consideran dependientes de sus smartphones.",
    "Las redes sociales tienen aspectos positivos y negativos, y debemos ser conscientes de ambos cuando utilicemos estas plataformas.",
    "El estudio de la adicción tecnológica es una de las áreas más relevantes de la investigación científica moderna."]
numero_secreto = random.randint(1, 100)
auto = {"Rolls-Royce" : "Rolls-Royce Phantom", 
        "Ferrari" : "Ferrari F40", 
        "Lamborghini" : "Lamborghini Aventador",
        "Chevrolet" : "Chevrolet Corvette", 
        "Porsche" : "Porsche 911", 
        "Mercedes-Benz" : "Mercedes-Benz Clase S",
        "Volkswagen" : "Volkswagen Beetle", 
        "BMW" : "BMW Serie 3", 
        "Tesla" : "Tesla Model S",
        }
brands_sources = {"Rolls-Royce" : ["https://www.carlogos.org/logo/Rolls-Royce-logo-640x550.jpg", "https://tse2.mm.bing.net/th/id/OIP.qplQbEsyUIqdHfIYb53wCgHaE8?pid=Api&P=0&h=180"],
                  "Ferrari" : ["https://www.carlogos.org/car-logos/ferrari-logo-2002-640.png", "https://tse1.mm.bing.net/th/id/OIP.JtNqYzG9IKxiJpEhoGSpQQHaEK?pid=Api&P=0&h=180"],
                  "Lamborghini" : ["https://www.carlogos.org/car-logos/lamborghini-logo-1998-640.png", "https://tse1.mm.bing.net/th/id/OIP.uEzjtB7gAhdWithOpbjlXwHaEK?pid=Api&P=0&h=180"],
                  "Chevrolet" : ["https://www.carlogos.org/logo/Chevrolet-logo-2013-640x281.jpg", "https://tse3.mm.bing.net/th/id/OIP.eSS9WhIMJNqGdRqYymNVOwHaEK?pid=Api&P=0&h=180"],
                  "Porsche" : ["https://www.carlogos.org/car-logos/porsche-logo-2014-full-640.png", "https://tse4.mm.bing.net/th/id/OIP.vfojk3lqlhBAEQmgmDVraQHaEK?pid=Api&P=0&h=180"],
                  "Mercedes-Benz" : ["https://www.carlogos.org/logo/Mercedes-Benz-logo-2011-640x369.jpg", "https://tse3.mm.bing.net/th/id/OIP.yEkb18xhPILMGc2Yxll39gHaE8?pid=Api&P=0&h=180"],
                  "Volkswagen" : ["https://www.carlogos.org/logo/Volkswagen-logo-2019-640x500.jpg", "https://tse2.mm.bing.net/th/id/OIP.lLxBnIbsPyRJJQQyYcBDgQHaFj?pid=Api&P=0&h=180"],
                  "BMW" : ["https://www.carlogos.org/car-logos/bmw-logo-2020-gray.png", "https://tse3.mm.bing.net/th/id/OIP.mTTCq-jCAs9IZEqlgTAosgHaEn?pid=Api&P=0&h=180"],
                  "Tesla" : ["https://www.carlogos.org/car-logos/tesla-logo-2007-full-640.png", "https://tse1.mm.bing.net/th/id/OIP.l9YIQOKp-oBRXTvFwhvFuAHaEK?pid=Api&P=0&h=180"]
}

cars_brands = ""
fam = ""
logo_src = ""
car_src = ""

@app.route("/")
def hello_world():
    return f'''<h1>Hello, World!</h1>
    <p>Sitio Creado por: {nombre} </p>
    <a href = "/datos">Ver Datos</a>
    <a href = "/brand">Ver Marca de Auto</a>
    '''

@app.route("/datos")
def datos():
    return f'''
    <h1>Este es un dato sobre la dependencia tecnologica</h1>
    <p>{random.choice(facts_list)}</p>
    <a href = "/datos">Ver Otros Datos</a>
    <a href = "/">Ir al inicio</a>
    <a href = "/color/blue">Ver Texto de Color</a>
    '''

@app.route("/color/<string:color>")
def color(color):
    return f'''
        <h1 style = "color: {color}">Este texto esta en el color {color}<h1>
        <a href = "/">Ir a inicio</a>
        '''

@app.route("/adivina/<int:num>")
def adivina(num):
    if num == numero_secreto:
        return "<h2> correcto adivinaste </h2>"
    else:
        return "<h2> Incorrecto no adivinaste </h2>"

@app.route("/brand")
def marca():
    global cars_brands, fam, logo_src, car_src
    cars_brands = random.choice(list(auto.keys()))
    fam = auto[cars_brands]
    logo_src = brands_sources[cars_brands][-2]
    car_src = brands_sources[cars_brands][-1]
    return f'''
    <h1>{cars_brands}</h1>
    <img src = "{logo_src}" alt = "Logo"></img>
    <h2>Su auto mas famoso es {fam}</h2>
    <img src = "{car_src}" alt = "Carro"></img>
    <a href = "/">Ir a inicio</a>
    <a href = "/brand">Ver otra marca de auto</a>
    '''

app.run(debug=True)
