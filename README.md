HTML
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GRAFICAS</title>
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #34495e;
            --accent: #3498db;
            --bg: #f4f7f6;
            --text: #333;
            --code-bg: #282c34;
            --white: #ffffff;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg);
            color: var(--text);
            line-height: 1.6;
            margin: 0;
            padding: 0;
        }

        .container {
            max-width: 1000px;
            margin: 40px auto;
            background: var(--white);
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }

        header {
            text-align: center;
            border-bottom: 3px solid var(--accent);
            margin-bottom: 40px;
            padding-bottom: 20px;
        }

        h1 { color: var(--primary); margin-bottom: 10px; }
        h2 { 
            color: var(--white); 
            background: var(--primary);
            padding: 10px 20px;
            border-radius: 5px;
            margin-top: 50px;
        }
        h3 { color: var(--accent); border-bottom: 1px solid #ddd; padding-bottom: 5px; }

        .intro-text {
            font-size: 1.1em;
            color: #666;
            margin-bottom: 30px;
        }

        .card {
            background: #fafafa;
            border: 1px solid #eee;
            border-radius: 10px;
            padding: 25px;
            margin-bottom: 30px;
        }

        .context-box {
            background-color: #e8f4fd;
            border-left: 5px solid var(--accent);
            padding: 15px;
            margin: 15px 0;
            font-style: italic;
        }

        pre {
            background-color: var(--code-bg);
            color: #abb2bf;
            padding: 20px;
            border-radius: 8px;
            overflow-x: auto;
            font-family: 'Consolas', 'Monaco', monospace;
            font-size: 14px;
            box-shadow: inset 0 0 10px rgba(0,0,0,0.3);
        }

        .img-placeholder {
            display: block;
            max-width: 100%;
            height: auto;
            margin: 20px auto;
            border-radius: 8px;
            border: 1px solid #ddd;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }

        th, td {
            text-align: left;
            padding: 12px;
            border-bottom: 1px solid #ddd;
        }

        th { background-color: var(--accent); color: white; }

        footer {
            text-align: center;
            margin-top: 50px;
            font-size: 0.9em;
            color: #888;
        }
    </style>
</head>
<body>

<div class="container">
    <header>
        <h1>Visualización de Datos con Matplotlib</h1>
        <p class="intro-text">Guía completa para la representación de variables cuantitativas y cualitativas en Probabilidad y Estadística.</p>
    </header>

    <section>
        <h2>1. Datos Cuantitativos Discretos</h2>
        <p>Representan conteos exactos con valores enteros. No admiten decimales ya que las unidades no pueden dividirse en el contexto analizado.</p>

        <div class="card">
            <h3>Gráfica de Barras: Libros Leídos</h3>
            <div class="context-box">
                <strong>Contexto Real:</strong> Hábitos de lectura en una muestra de 5 estudiantes para medir el acceso cultural.<br>
                <strong>Análisis Estadístico:</strong> Permite comparar la frecuencia absoluta y detectar valores atípicos (outliers) rápidamente.
            </div>
            <pre><code>import matplotlib.pyplot as plt

estudiantes = ["Ana", "Luis", "Carlos", "Marta", "Sofía"]
libros = [1, 3, 2, 4, 2]

plt.bar(estudiantes, libros)
plt.title("Libros leídos por estudiante")
plt.xlabel("Estudiantes")
plt.ylabel("Cantidad de libros")
plt.show()</code></pre>
            <img src="IMAGENES/IMA1CUAN.png" alt="Gráfica de Barras Discreta" class="img-placeholder">
        </div>

        <div class="card">
            <h3>Gráfica de Línea: Tareas Entregadas</h3>
            <div class="context-box">
                <strong>Contexto Real:</strong> Seguimiento del cumplimiento escolar durante una semana.<br>
                <strong>Análisis Estadístico:</strong> Análisis de tendencias temporales para observar la evolución del compromiso del grupo.
            </div>
            <pre><code>import matplotlib.pyplot as plt

dias = [1, 2, 3, 4, 5, 6]
tareas = [2, 4, 3, 5, 4, 6]

plt.plot(dias, tareas, marker='o')
plt.title("Tareas entregadas por día")
plt.xlabel("Día")
plt.ylabel("Cantidad de tareas")
plt.show()</code></pre>
            <img src="IMAGENES/IMA2CUAN.png" alt="Gráfica de Línea" class="img-placeholder">
        </div>

        <div class="card">
            <h3>Gráfica de Pastel: Distribución de Votos</h3>
            <div class="context-box">
                <strong>Contexto Real:</strong> Elecciones internas para representante estudiantil.<br>
                <strong>Análisis Estadístico:</strong> Representación de la frecuencia relativa. Ideal para visualizar la proporción de cada candidato respecto al total.
            </div>
            <pre><code>import matplotlib.pyplot as plt

candidatos = ["A", "B", "C", "D"]
votos = [10, 15, 8, 12]

plt.pie(votos, labels=candidatos, autopct="%1.1f%%")
plt.title("Distribución de votos")
plt.show()</code></pre>
            <img src="IMAGENES/IMA3CUAN.png" alt="Gráfica de Pastel" class="img-placeholder">
        </div>
    </section>

    <section>
        <h2>2. Datos Cuantitativos Continuos</h2>
        <p>Resultan de mediciones y pueden tomar infinitos valores dentro de un rango (incluyen decimales). Su estudio es clave para entender la variabilidad biológica y física.</p>

        <div class="card">
            <h3>Histograma: Distribución de Estaturas</h3>
            <div class="context-box">
                <strong>Contexto Real:</strong> Análisis biométrico de una población estudiantil para salud pública.<br>
                <strong>Análisis Estadístico:</strong> Agrupa datos en intervalos. Permite observar si la población sigue una Distribución Normal.
            </div>
            
            <pre><code>import matplotlib.pyplot as plt

estaturas = [1.60, 1.72, 1.68, 1.75, 1.80, 1.65, 1.70, 1.78, 1.69, 1.74]

plt.hist(estaturas, bins=5, edgecolor='black')
plt.title("Distribución de estaturas")
plt.xlabel("Estatura (m)")
plt.ylabel("Frecuencia")
plt.show()</code></pre>
            <img src="IMAGENES/IMA4CON.png" alt="Histograma de estaturas" class="img-placeholder">
        </div>

        <div class="card">
            <h3>Gráfica de Dispersión: Peso vs Estatura</h3>
            <div class="context-box">
                <strong>Contexto Real:</strong> Estudio de la relación fisiológica entre dos variables métricas.<br>
                <strong>Análisis Estadístico:</strong> Identificación de correlaciones. Es la base para construir modelos de regresión lineal.
            </div>
            

[Image of a scatter plot showing positive correlation]

            <pre><code>import matplotlib.pyplot as plt

estatura = [1.60, 1.65, 1.70, 1.75, 1.80]
peso = [55.2, 60.5, 68.0, 72.3, 80.1]

plt.scatter(estatura, peso)
plt.title("Relación entre estatura y peso")
plt.xlabel("Estatura (m)")
plt.ylabel("Peso (kg)")
plt.show()</code></pre>
            <img src="IMAGENES/IMA6CON.png" alt="Gráfica de Dispersión" class="img-placeholder">
        </div>
    </section>

    <section>
        <h2>3. Datos Cualitativos</h2>
        <p>Describen atributos, categorías o cualidades no numéricas. Se analizan mediante la frecuencia de sus categorías.</p>

        <div class="card">
            <h3>Barras Horizontales: Marcas de Celular</h3>
            <div class="context-box">
                <strong>Contexto Real:</strong> Estudio de mercado sobre preferencia de marcas tecnológicas.<br>
                <strong>Análisis Estadístico:</strong> Se usa para identificar la Moda. La orientación horizontal facilita la lectura de los nombres de las marcas.
            </div>
            <pre><code>import matplotlib.pyplot as plt

marcas = ["Samsung", "Apple", "Xiaomi"]
frecuencia = [4, 2, 2]

plt.barh(marcas, frecuencia)
plt.title("Marca de celular más utilizada")
plt.xlabel("Frecuencia")
plt.show()</code></pre>
            <img src="IMAGENES/IMA9CUAL.png" alt="Barras Horizontales" class="img-placeholder">
        </div>
    </section>

    <section>
        <h2>Resumen de Aplicación</h2>
        <table>
            <thead>
                <tr>
                    <th>Tipo de Variable</th>
                    <th>Gráfica Sugerida</th>
                    <th>Uso Principal</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>Cuantitativa Discreta</td>
                    <td>Barras / Línea</td>
                    <td>Conteos y tendencias.</td>
                </tr>
                <tr>
                    <td>Cuantitativa Continua</td>
                    <td>Histograma / Dispersión</td>
                    <td>Distribuciones y correlaciones.</td>
                </tr>
                <tr>
                    <td>Cualitativa</td>
                    <td>Pastel / Barras</td>
                    <td>Proporciones y categorías dominantes.</td>
                </tr>
            </tbody>
        </table>
    </section>

    <footer>
    </footer>
</div>

</body>
</html>
