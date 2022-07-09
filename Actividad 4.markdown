---
jupyter:
  kernelspec:
    display_name: Python 3 (ipykernel)
    language: python
    name: python3
  language_info:
    codemirror_mode:
      name: ipython
      version: 3
    file_extension: .py
    mimetype: text/x-python
    name: python
    nbconvert_exporter: python
    pygments_lexer: ipython3
    version: 3.9.12
  nbformat: 4
  nbformat_minor: 5
---

::: {.cell .markdown}
# AD4: Uso la API del COVID-19 con Pandas
:::

::: {.cell .markdown}
Para comenzar, definiremos una API. Las siglas provienen del inglés
*application programming interface* o interfaz de programación de
aplicaciones la que permite el intercambio de información entre dos
componentes de software independientes.

Para continuar con el ejercicio, me conecto a la API
<https://api.covid19api.com/> que usaremos para esta actividad.
:::

::: {.cell .markdown}
## Instalación de Pandas
:::

::: {.cell .markdown}
Para cargar los datos del a API, así como para trabajar con ellos como
un dataframe, se utiliza la librería Pandas, la cual instala a
continuación.
:::

::: {.cell .code execution_count="1"}
``` {.python}
!pip install pandas
```

::: {.output .stream .stdout}
    Requirement already satisfied: pandas in c:\users\evole\anaconda3\lib\site-packages (1.4.2)
    Requirement already satisfied: numpy>=1.18.5 in c:\users\evole\anaconda3\lib\site-packages (from pandas) (1.21.5)
    Requirement already satisfied: python-dateutil>=2.8.1 in c:\users\evole\anaconda3\lib\site-packages (from pandas) (2.8.2)
    Requirement already satisfied: pytz>=2020.1 in c:\users\evole\anaconda3\lib\site-packages (from pandas) (2021.3)
    Requirement already satisfied: six>=1.5 in c:\users\evole\anaconda3\lib\site-packages (from python-dateutil>=2.8.1->pandas) (1.16.0)
:::
:::

::: {.cell .markdown}
## Configuración de Pandas
:::

::: {.cell .markdown}
Lo siguente, tras la instalación de la librería Pandas, es importarla,
operación que realizó abajo.
:::

::: {.cell .code execution_count="2"}
``` {.python}
import pandas as pd 
```
:::

::: {.cell .markdown}
# Variables
:::

::: {.cell .markdown}
Se utiliza la variable `url`, que contiene la lista de los países.
:::

::: {.cell .code execution_count="3"}
``` {.python}
url = 'https://api.covid19api.com/countries'
```
:::

::: {.cell .markdown}
Para comprobar que funciono, invoco a `url` y verifico que me sale
muestra el valor de la entidad.
:::

::: {.cell .code execution_count="4"}
``` {.python}
url
```

::: {.output .execute_result execution_count="4"}
    'https://api.covid19api.com/countries'
:::
:::

::: {.cell .markdown}
## Creación de *Dataframe*
:::

::: {.cell .markdown}
Luego de la comprobación del funcionamiento de la `url`, utilizo la
función de Pandas `read_json()`, la cual es capaz de leer el `JSON` que
ofrece la API.
:::

::: {.cell .code execution_count="5"}
``` {.python}
df = pd.read_json(url)
```
:::

::: {.cell .markdown}
Tras esto, invoco el *Dataframe* para comprobar que se raelizo la
importanción. El éxito de la operación muestra a una tabla con 248 filas
y tres columnas.
:::

::: {.cell .code execution_count="6"}
``` {.python}
df
```

::: {.output .execute_result execution_count="6"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Slug</th>
      <th>ISO2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Gibraltar</td>
      <td>gibraltar</td>
      <td>GI</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Oman</td>
      <td>oman</td>
      <td>OM</td>
    </tr>
    <tr>
      <th>2</th>
      <td>France</td>
      <td>france</td>
      <td>FR</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jersey</td>
      <td>jersey</td>
      <td>JE</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Mali</td>
      <td>mali</td>
      <td>ML</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>243</th>
      <td>Puerto Rico</td>
      <td>puerto-rico</td>
      <td>PR</td>
    </tr>
    <tr>
      <th>244</th>
      <td>Papua New Guinea</td>
      <td>papua-new-guinea</td>
      <td>PG</td>
    </tr>
    <tr>
      <th>245</th>
      <td>Saint Pierre and Miquelon</td>
      <td>saint-pierre-and-miquelon</td>
      <td>PM</td>
    </tr>
    <tr>
      <th>246</th>
      <td>Timor-Leste</td>
      <td>timor-leste</td>
      <td>TL</td>
    </tr>
    <tr>
      <th>247</th>
      <td>Montenegro</td>
      <td>montenegro</td>
      <td>ME</td>
    </tr>
  </tbody>
</table>
<p>248 rows × 3 columns</p>
</div>
```
:::
:::

::: {.cell .markdown}
El código de arriba nos mostró los primeros y últimos cinco elementos de
las filas. Por tratarse de `JSON`, el conteo se inicia con el 0 que
ocupa la posición primera; se agrega una columna de control de la
librería.
:::

::: {.cell .markdown}
Ahora quiero sacar específicamente los datos de España. Como los nombres
de los Estados están en inglés, España está escrito como *Spain*. Como
hay una columna llamada *country* creo una lista nueva para que solo se
muestra los datos de España.
:::

::: {.cell .code execution_count="7"}
``` {.python}
df[df['Country'] == 'Spain']
```

::: {.output .execute_result execution_count="7"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Slug</th>
      <th>ISO2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>141</th>
      <td>Spain</td>
      <td>spain</td>
      <td>ES</td>
    </tr>
  </tbody>
</table>
</div>
```
:::
:::

::: {.cell .markdown}
Me sale que el ID de *Spain*, en la columna de control de Pandas, es
201.
:::

::: {.cell .markdown}
Ahora creo una nueva `URL`, de la misma API, para sacar solo los datos
que corresponden a España, pero en tiempo real; esto se hizo en la
primera linea.

En la segunda linea coloco un *Dataframe* que leerá los datos de la
`URL` que especifiqué.

Ya en la tercera línea, invocaré el *Dataframe* para comprobarlo.
:::

::: {.cell .code execution_count="8"}
``` {.python}
url_rt_es = 'https://api.covid19api.com/country/spain/status/confirmed/live'
df_rt_es = pd.read_json(url_rt_es)
df_rt_es
```

::: {.output .execute_result execution_count="8"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>CountryCode</th>
      <th>Province</th>
      <th>City</th>
      <th>CityCode</th>
      <th>Lat</th>
      <th>Lon</th>
      <th>Cases</th>
      <th>Status</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-22 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-23 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-24 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-25 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-26 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>893</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12818184</td>
      <td>confirmed</td>
      <td>2022-07-03 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>894</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12818184</td>
      <td>confirmed</td>
      <td>2022-07-04 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>895</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12890002</td>
      <td>confirmed</td>
      <td>2022-07-05 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>896</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12890002</td>
      <td>confirmed</td>
      <td>2022-07-06 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>897</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12890002</td>
      <td>confirmed</td>
      <td>2022-07-07 00:00:00+00:00</td>
    </tr>
  </tbody>
</table>
<p>898 rows × 10 columns</p>
</div>
```
:::
:::

::: {.cell .markdown}
El código de arriba nos mostró los primeros y últimos cinco elementos de
las filas que se corresponden para España. Al igual que anterior, por
tratarse de JSON, el conteo se inicia con el 0 que ocupa la posición
primera; se agrega una columna de control de la librería.
:::

::: {.cell .markdown}
### Cabecera y cola
:::

::: {.cell .markdown}
Para acceder a la cabecera se usa la función `head()`, pero con el
*DataFrame* `df_rt_es.head()`.
:::

::: {.cell .code execution_count="9" scrolled="true"}
``` {.python}
df_rt_es.head()
```

::: {.output .execute_result execution_count="9"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>CountryCode</th>
      <th>Province</th>
      <th>City</th>
      <th>CityCode</th>
      <th>Lat</th>
      <th>Lon</th>
      <th>Cases</th>
      <th>Status</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-22 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-23 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-24 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-25 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-26 00:00:00+00:00</td>
    </tr>
  </tbody>
</table>
</div>
```
:::
:::

::: {.cell .markdown}
Para que me muestre solo los datos del inicio usaré el DataFrame
`df_rt_es.tail()`.
:::

::: {.cell .code execution_count="10"}
``` {.python}
df_rt_es.tail()
```

::: {.output .execute_result execution_count="10"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>CountryCode</th>
      <th>Province</th>
      <th>City</th>
      <th>CityCode</th>
      <th>Lat</th>
      <th>Lon</th>
      <th>Cases</th>
      <th>Status</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>893</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12818184</td>
      <td>confirmed</td>
      <td>2022-07-03 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>894</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12818184</td>
      <td>confirmed</td>
      <td>2022-07-04 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>895</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12890002</td>
      <td>confirmed</td>
      <td>2022-07-05 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>896</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12890002</td>
      <td>confirmed</td>
      <td>2022-07-06 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>897</th>
      <td>Spain</td>
      <td>ES</td>
      <td></td>
      <td></td>
      <td></td>
      <td>40.46</td>
      <td>-3.75</td>
      <td>12890002</td>
      <td>confirmed</td>
      <td>2022-07-07 00:00:00+00:00</td>
    </tr>
  </tbody>
</table>
</div>
```
:::
:::

::: {.cell .markdown}
### Creo un gráfico
:::

::: {.cell .markdown}
Ahora realizaré un gráfico con la cantidad de casos y la fecha. Para
ello convertiré la columna de control de España. Transformo la columna
de fecha con la de control, pidiéndole que me muestra los casos del país
desde el 20 de enero de 2020 al 29 de junio de 2022.

Para todo esto usaré la expresión
`df_rt_es.set_index('Date')['Cases'].plot(title="Casos de COVID-19 en España desde el 20/01/2020 hasta el 29/06/2022")`.
Para evitar inconvenientes con Anaconda3, a la variable le pondré el
nombre de `plot_rt_es`.
:::

::: {.cell .code execution_count="15"}
``` {.python}
df_rt_es.set_index('Date') ['Cases'].plot(title="Casos de COVID-19 en España desde el 20/1/2020 hasta el 8/7/2022")
```

::: {.output .execute_result execution_count="15"}
    <AxesSubplot:title={'center':'Casos de COVID-19 en España desde el 20/1/2020 hasta el 8/7/2022'}, xlabel='Date'>
:::

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/a42fa5b67cabd701ea97ecd22a727b5fdaab88ef.png)
:::
:::

::: {.cell .markdown}
## Repetir el proceso con Panamá
:::

::: {.cell .markdown}
Debido a que tengo una columna de países, creo una lista nueva que
seleccione solo los identificadores similares a Panama, sin tilde porque
está en inglés.
:::

::: {.cell .code execution_count="12"}
``` {.python}
df[df['Country'] == 'Panama']
```

::: {.output .execute_result execution_count="12"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Slug</th>
      <th>ISO2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>190</th>
      <td>Panama</td>
      <td>panama</td>
      <td>PA</td>
    </tr>
  </tbody>
</table>
</div>
```
:::
:::

::: {.cell .markdown}
Me sale que el ID de Panama, en la columna de control de Pandas, es 184.
Ahora creo una nueva URL, de la misma API, para sacar solo los datos que
corresponden a Panamá en tiempo real.

En la segunda linea coloco un *Dataframe* que leerá los datos de la
`URL` que especifiqué. Ya en la tercera línea, invocaré el *Dataframe*
para comprobarlo.
:::

::: {.cell .code execution_count="13"}
``` {.python}
url_rt_pa = 'https://api.covid19api.com/country/panama/status/confirmed/live'
df_rt_pa = pd.read_json(url_rt_pa)
df_rt_pa
```

::: {.output .execute_result execution_count="13"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>CountryCode</th>
      <th>Province</th>
      <th>City</th>
      <th>CityCode</th>
      <th>Lat</th>
      <th>Lon</th>
      <th>Cases</th>
      <th>Status</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-22 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-23 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-24 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-25 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-26 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>894</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>925254</td>
      <td>confirmed</td>
      <td>2022-07-04 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>895</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>925254</td>
      <td>confirmed</td>
      <td>2022-07-05 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>896</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>925254</td>
      <td>confirmed</td>
      <td>2022-07-06 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>897</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>925254</td>
      <td>confirmed</td>
      <td>2022-07-07 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>898</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>925254</td>
      <td>confirmed</td>
      <td>2022-07-08 00:00:00+00:00</td>
    </tr>
  </tbody>
</table>
<p>899 rows × 10 columns</p>
</div>
```
:::
:::

::: {.cell .markdown}
### El gráfico de Panamá
:::

::: {.cell .markdown}
Ahora realizaré un gráfico con la cantidad de casos y la fecha. Como en
el caso de España, convertiré la columna de control de España.
Transformo la columna de fecha con la de control, pidiéndole que me
muestra los casos del país desde el 20 de enero de 2020 al 29 de junio
de 2022.

Para todo esto usaré la expresión
`df_rt_pa.set_index('Date')['Cases'].plot(title="Casos de COVID-19 en Panamá desde el 20/01/2020 hasta el 29/06/2022")`.
:::

::: {.cell .code execution_count="16"}
``` {.python}
df_rt_pa.set_index('Date')['Cases'].plot(title="Casos de COVID-19 en Panamá desde el 20/01/2020 hasta el 8/7/2022")
```

::: {.output .execute_result execution_count="16"}
    <AxesSubplot:title={'center':'Casos de COVID-19 en Panamá desde el 20/01/2020 hasta el 8/7/2022'}, xlabel='Date'>
:::

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/f21f7afe485dd4a600546d2d88e4d1d2caee4b75.png)
:::
:::

::: {.cell .markdown}
#### Gráfico de área con datos de Panamá
:::

::: {.cell .markdown}
Si agregamos al final `kind="area"` se visualizará un gráfico de área y
con `kind="bar"` el gráfico de barras.
:::

::: {.cell .markdown}
A continuación, el gráfico de area:
:::

::: {.cell .code execution_count="21"}
``` {.python}
plot_rt_pa = df_rt_pa.set_index('Date')['Cases'].plot(title="Casos de COVID-19 en Panamá desde 20/01/2020 hasta 08/07/2022",kind="area")
```

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/2d29fde4ef91fccc68a4bcefe52bceba15f10599.png)
:::
:::

::: {.cell .markdown}
El gráfico de barras:
:::

::: {.cell .code execution_count="20"}
``` {.python}
plot_rt_pa = df_rt_pa.set_index('Date')['Cases'].plot(title="Casos de COVID-19 en Panamá desde 20/01/2020 hasta 08/07/2022",kind="bar")
```

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/dd8bd9de1cad26162f2188de43ca96785f02c078.png)
:::
:::

::: {.cell .markdown}
# Plotear a España y Panamá
:::

::: {.cell .markdown}
Para plotear a los países se identifican otra vez las variables previas
de lectura de JSON de las dos URLs para no tener que repetir el proceso
desde arriba al cerrar el documento.
:::

::: {.cell .code execution_count="22"}
``` {.python}
df_rt_pa = pd.read_json(url_rt_pa)
df_rt_es = pd.read_json(url_rt_es)
```
:::

::: {.cell .markdown}
Los casos son separados por fecha según el país y se imprime para
confirmar la gráfica. Primero Panamá:
:::

::: {.cell .code execution_count="23"}
``` {.python}
casos_pa = df_rt_pa.set_index('Date')['Cases']
casos_pa.plot(title="Casos de COVID-19 en Panamá")
```

::: {.output .execute_result execution_count="23"}
    <AxesSubplot:title={'center':'Casos de COVID-19 en Panamá'}, xlabel='Date'>
:::

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/e7a0af5b7b3cac772862aaca5ecaccccb295e9d4.png)
:::
:::

::: {.cell .markdown}
Ahora España:
:::

::: {.cell .code execution_count="25"}
``` {.python}
casos_es = df_rt_es.set_index('Date')['Cases']
casos_pa.plot(title="Casos de Covid-19 en España")
```

::: {.output .execute_result execution_count="25"}
    <AxesSubplot:title={'center':'Casos de Covid-19 en España'}, xlabel='Date'>
:::

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/03b3560cfd6ad3145ceee8d65df0d9ef0ad9dc0c.png)
:::
:::

::: {.cell .markdown}
Ahora concatenamos las dos tablas por fechas y casos de Panamá y España.
:::

::: {.cell .code execution_count="27"}
``` {.python}
pa_vs_es = pd.concat([casos_es,casos_pa],axis=1)
pa_vs_es
```

::: {.output .execute_result execution_count="27"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Cases</th>
      <th>Cases</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2020-01-22 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-23 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-24 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-25 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-26 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2022-07-04 00:00:00+00:00</th>
      <td>12818184.0</td>
      <td>925254</td>
    </tr>
    <tr>
      <th>2022-07-05 00:00:00+00:00</th>
      <td>12890002.0</td>
      <td>925254</td>
    </tr>
    <tr>
      <th>2022-07-06 00:00:00+00:00</th>
      <td>12890002.0</td>
      <td>925254</td>
    </tr>
    <tr>
      <th>2022-07-07 00:00:00+00:00</th>
      <td>12890002.0</td>
      <td>925254</td>
    </tr>
    <tr>
      <th>2022-07-08 00:00:00+00:00</th>
      <td>NaN</td>
      <td>925254</td>
    </tr>
  </tbody>
</table>
<p>899 rows × 2 columns</p>
</div>
```
:::
:::

::: {.cell .markdown}
Ahora marco las columnas con el nombre del país y se muestra la gráfica
con los datos nombrados.
:::

::: {.cell .code execution_count="28"}
``` {.python}
pa_vs_es.columns= ['España','Panamá']
pa_vs_es
```

::: {.output .execute_result execution_count="28"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>España</th>
      <th>Panamá</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2020-01-22 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-23 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-24 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-25 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-26 00:00:00+00:00</th>
      <td>0.0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2022-07-04 00:00:00+00:00</th>
      <td>12818184.0</td>
      <td>925254</td>
    </tr>
    <tr>
      <th>2022-07-05 00:00:00+00:00</th>
      <td>12890002.0</td>
      <td>925254</td>
    </tr>
    <tr>
      <th>2022-07-06 00:00:00+00:00</th>
      <td>12890002.0</td>
      <td>925254</td>
    </tr>
    <tr>
      <th>2022-07-07 00:00:00+00:00</th>
      <td>12890002.0</td>
      <td>925254</td>
    </tr>
    <tr>
      <th>2022-07-08 00:00:00+00:00</th>
      <td>NaN</td>
      <td>925254</td>
    </tr>
  </tbody>
</table>
<p>899 rows × 2 columns</p>
</div>
```
:::
:::

::: {.cell .markdown}
Ahora imprimimos para visualizar la comparación entre Panamá y España.
:::

::: {.cell .code execution_count="30"}
``` {.python}
pa_vs_es.plot(title="Comparación de los casos COVID-19 España-Panamá")
```

::: {.output .execute_result execution_count="30"}
    <AxesSubplot:title={'center':'Comparación de los casos COVID-19 España-Panamá'}, xlabel='Date'>
:::

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/028e1e3146341836c84b548e02e4d767afae8dcd.png)
:::
:::

::: {.cell .markdown}
Usamos la función `pa_vs_es.to_csv('pa_vs_cr.csv')` para descargar los
archivos en formato CSV (del inglés *comma-separated values*). La parte
de `pa_vs_cr` el nombre de la tabla comparativa.
:::

::: {.cell .code execution_count="31"}
``` {.python}
pa_vs_es.to_csv('pa_vs_cr.csv')
%ls
```

::: {.output .stream .stdout}
     Volume in drive C is Windows-SSD
     Volume Serial Number is 3E46-6E69

     Directory of C:\Users\Evole\gcuevasbenitez-web

    07/08/2022  08:05 PM    <DIR>          .
    07/08/2022  08:05 PM    <DIR>          ..
    07/01/2022  09:34 PM    <DIR>          .ipynb_checkpoints
    06/26/2022  11:52 AM             3,592 ad1.md
    06/27/2022  10:26 PM             3,751 ad2.md
    06/26/2022  01:41 PM            13,640 ad3.ipynb
    06/26/2022  06:39 PM           136,123 adtres.ipynb
    06/27/2022  10:13 PM           115,058 adtres.md
    06/26/2022  06:40 PM           136,123 adtres-Copy1.ipynb
    07/08/2022  08:04 PM           186,558 api-covid-pandas.ipynb
    07/08/2022  08:05 PM            38,677 pa_vs_cr.csv
    06/27/2022  10:26 PM               480 README.md
                   9 File(s)        634,002 bytes
                   3 Dir(s)  50,100,957,184 bytes free
:::
:::

::: {.cell .markdown}
Si ahora quiero mostrar la gráfica en PNG (imagen) o SVG (gráficos
vectoriales) se colocan los códigos a continuación:
:::

::: {.cell .code execution_count="32"}
``` {.python}
import matplotlib.pyplot as plt
pa_vs_es.plot(title="Panamá vs España")
plt.savefig('pa_vs_es.png')
%ls
```

::: {.output .stream .stdout}
     Volume in drive C is Windows-SSD
     Volume Serial Number is 3E46-6E69

     Directory of C:\Users\Evole\gcuevasbenitez-web

    07/08/2022  08:06 PM    <DIR>          .
    07/08/2022  08:06 PM    <DIR>          ..
    07/01/2022  09:34 PM    <DIR>          .ipynb_checkpoints
    06/26/2022  11:52 AM             3,592 ad1.md
    06/27/2022  10:26 PM             3,751 ad2.md
    06/26/2022  01:41 PM            13,640 ad3.ipynb
    06/26/2022  06:39 PM           136,123 adtres.ipynb
    06/27/2022  10:13 PM           115,058 adtres.md
    06/26/2022  06:40 PM           136,123 adtres-Copy1.ipynb
    07/08/2022  08:05 PM           187,885 api-covid-pandas.ipynb
    07/08/2022  08:05 PM            38,677 pa_vs_cr.csv
    07/08/2022  08:06 PM            13,689 pa_vs_es.png
    06/27/2022  10:26 PM               480 README.md
                  10 File(s)        649,018 bytes
                   3 Dir(s)  50,102,693,888 bytes free
:::

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/3e1add072ab3b9a5d4013dc8a66f35ef5614c288.png)
:::
:::

::: {.cell .code execution_count="33"}
``` {.python}
pa_vs_es.plot(title="Panamá vs España")
plt.savefig("pa_vs_es.svg", format="svg")
%ls
```

::: {.output .stream .stdout}
     Volume in drive C is Windows-SSD
     Volume Serial Number is 3E46-6E69

     Directory of C:\Users\Evole\gcuevasbenitez-web

    07/08/2022  08:07 PM    <DIR>          .
    07/08/2022  08:07 PM    <DIR>          ..
    07/01/2022  09:34 PM    <DIR>          .ipynb_checkpoints
    06/26/2022  11:52 AM             3,592 ad1.md
    06/27/2022  10:26 PM             3,751 ad2.md
    06/26/2022  01:41 PM            13,640 ad3.ipynb
    06/26/2022  06:39 PM           136,123 adtres.ipynb
    06/27/2022  10:13 PM           115,058 adtres.md
    06/26/2022  06:40 PM           136,123 adtres-Copy1.ipynb
    07/08/2022  08:06 PM           207,530 api-covid-pandas.ipynb
    07/08/2022  08:05 PM            38,677 pa_vs_cr.csv
    07/08/2022  08:06 PM            13,689 pa_vs_es.png
    07/08/2022  08:07 PM            41,471 pa_vs_es.svg
    06/27/2022  10:26 PM               480 README.md
                  11 File(s)        710,134 bytes
                   3 Dir(s)  50,102,476,800 bytes free
:::

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/3e1add072ab3b9a5d4013dc8a66f35ef5614c288.png)
:::
:::

::: {.cell .markdown}
# Comparar los casos en Centroamérica
:::

::: {.cell .markdown}
Los países a comparar, según los casos de COVID-19, son Panamá, Costa
Rica, Nicaragua, Guatemala, El Salvador y Honduras. Por lo que repito el
mismo proceso para cada uno de ellos, según hice más arriba con Panamá y
España.
:::

::: {.cell .code execution_count="34"}
``` {.python}
df[df['Country'] == 'Panama']
```

::: {.output .execute_result execution_count="34"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Slug</th>
      <th>ISO2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>190</th>
      <td>Panama</td>
      <td>panama</td>
      <td>PA</td>
    </tr>
  </tbody>
</table>
</div>
```
:::
:::

::: {.cell .code execution_count="35"}
``` {.python}
df[df['Country'] == 'Costa Rica']
```

::: {.output .execute_result execution_count="35"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Slug</th>
      <th>ISO2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>242</th>
      <td>Costa Rica</td>
      <td>costa-rica</td>
      <td>CR</td>
    </tr>
  </tbody>
</table>
</div>
```
:::
:::

::: {.cell .code execution_count="36"}
``` {.python}
df[df['Country'] == 'Nicaragua']
```

::: {.output .execute_result execution_count="36"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Slug</th>
      <th>ISO2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>36</th>
      <td>Nicaragua</td>
      <td>nicaragua</td>
      <td>NI</td>
    </tr>
  </tbody>
</table>
</div>
```
:::
:::

::: {.cell .code execution_count="37"}
``` {.python}
df[df['Country'] == 'Guatemala']
```

::: {.output .execute_result execution_count="37"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Slug</th>
      <th>ISO2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>239</th>
      <td>Guatemala</td>
      <td>guatemala</td>
      <td>GT</td>
    </tr>
  </tbody>
</table>
</div>
```
:::
:::

::: {.cell .code execution_count="38"}
``` {.python}
df[df['Country'] == 'El Salvador']
```

::: {.output .execute_result execution_count="38"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Slug</th>
      <th>ISO2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>139</th>
      <td>El Salvador</td>
      <td>el-salvador</td>
      <td>SV</td>
    </tr>
  </tbody>
</table>
</div>
```
:::
:::

::: {.cell .code execution_count="39"}
``` {.python}
df[df['Country'] == 'Honduras']
```

::: {.output .execute_result execution_count="39"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>Slug</th>
      <th>ISO2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>91</th>
      <td>Honduras</td>
      <td>honduras</td>
      <td>HN</td>
    </tr>
  </tbody>
</table>
</div>
```
:::
:::

::: {.cell .code}
``` {.python}
Ahora, con la URL de cada país defino la variable y le indico a JSON para buscar las URL de las tablas.
```
:::

::: {.cell .code execution_count="40"}
``` {.python}
url_rt_pa = 'https://api.covid19api.com/country/panama/status/confirmed/live'
df_rt_pa = pd.read_json(url_rt_pa)
df_rt_pa
```

::: {.output .execute_result execution_count="40"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>CountryCode</th>
      <th>Province</th>
      <th>City</th>
      <th>CityCode</th>
      <th>Lat</th>
      <th>Lon</th>
      <th>Cases</th>
      <th>Status</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-22 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-23 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-24 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-25 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-26 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>894</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>925254</td>
      <td>confirmed</td>
      <td>2022-07-04 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>895</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>925254</td>
      <td>confirmed</td>
      <td>2022-07-05 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>896</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>925254</td>
      <td>confirmed</td>
      <td>2022-07-06 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>897</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>925254</td>
      <td>confirmed</td>
      <td>2022-07-07 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>898</th>
      <td>Panama</td>
      <td>PA</td>
      <td></td>
      <td></td>
      <td></td>
      <td>8.54</td>
      <td>-80.78</td>
      <td>925254</td>
      <td>confirmed</td>
      <td>2022-07-08 00:00:00+00:00</td>
    </tr>
  </tbody>
</table>
<p>899 rows × 10 columns</p>
</div>
```
:::
:::

::: {.cell .code execution_count="41"}
``` {.python}
url_rt_cr = 'https://api.covid19api.com/country/costa-rica/status/confirmed/live'
df_rt_cr = pd.read_json(url_rt_cr)
df_rt_cr
```

::: {.output .execute_result execution_count="41"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>CountryCode</th>
      <th>Province</th>
      <th>City</th>
      <th>CityCode</th>
      <th>Lat</th>
      <th>Lon</th>
      <th>Cases</th>
      <th>Status</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Costa Rica</td>
      <td>CR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>9.75</td>
      <td>-83.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-22 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Costa Rica</td>
      <td>CR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>9.75</td>
      <td>-83.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-23 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Costa Rica</td>
      <td>CR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>9.75</td>
      <td>-83.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-24 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Costa Rica</td>
      <td>CR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>9.75</td>
      <td>-83.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-25 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Costa Rica</td>
      <td>CR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>9.75</td>
      <td>-83.75</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-26 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>894</th>
      <td>Costa Rica</td>
      <td>CR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>9.75</td>
      <td>-83.75</td>
      <td>904934</td>
      <td>confirmed</td>
      <td>2022-07-04 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>895</th>
      <td>Costa Rica</td>
      <td>CR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>9.75</td>
      <td>-83.75</td>
      <td>904934</td>
      <td>confirmed</td>
      <td>2022-07-05 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>896</th>
      <td>Costa Rica</td>
      <td>CR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>9.75</td>
      <td>-83.75</td>
      <td>904934</td>
      <td>confirmed</td>
      <td>2022-07-06 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>897</th>
      <td>Costa Rica</td>
      <td>CR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>9.75</td>
      <td>-83.75</td>
      <td>904934</td>
      <td>confirmed</td>
      <td>2022-07-07 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>898</th>
      <td>Costa Rica</td>
      <td>CR</td>
      <td></td>
      <td></td>
      <td></td>
      <td>9.75</td>
      <td>-83.75</td>
      <td>904934</td>
      <td>confirmed</td>
      <td>2022-07-08 00:00:00+00:00</td>
    </tr>
  </tbody>
</table>
<p>899 rows × 10 columns</p>
</div>
```
:::
:::

::: {.cell .code execution_count="42"}
``` {.python}
url_rt_ni = 'https://api.covid19api.com/country/nicaragua/status/confirmed/live'
df_rt_ni = pd.read_json(url_rt_ni)
df_rt_ni
```

::: {.output .execute_result execution_count="42"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>CountryCode</th>
      <th>Province</th>
      <th>City</th>
      <th>CityCode</th>
      <th>Lat</th>
      <th>Lon</th>
      <th>Cases</th>
      <th>Status</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Nicaragua</td>
      <td>NI</td>
      <td></td>
      <td></td>
      <td></td>
      <td>12.87</td>
      <td>-85.21</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-22 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nicaragua</td>
      <td>NI</td>
      <td></td>
      <td></td>
      <td></td>
      <td>12.87</td>
      <td>-85.21</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-23 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Nicaragua</td>
      <td>NI</td>
      <td></td>
      <td></td>
      <td></td>
      <td>12.87</td>
      <td>-85.21</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-24 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Nicaragua</td>
      <td>NI</td>
      <td></td>
      <td></td>
      <td></td>
      <td>12.87</td>
      <td>-85.21</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-25 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Nicaragua</td>
      <td>NI</td>
      <td></td>
      <td></td>
      <td></td>
      <td>12.87</td>
      <td>-85.21</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-26 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>894</th>
      <td>Nicaragua</td>
      <td>NI</td>
      <td></td>
      <td></td>
      <td></td>
      <td>12.87</td>
      <td>-85.21</td>
      <td>14690</td>
      <td>confirmed</td>
      <td>2022-07-04 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>895</th>
      <td>Nicaragua</td>
      <td>NI</td>
      <td></td>
      <td></td>
      <td></td>
      <td>12.87</td>
      <td>-85.21</td>
      <td>14690</td>
      <td>confirmed</td>
      <td>2022-07-05 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>896</th>
      <td>Nicaragua</td>
      <td>NI</td>
      <td></td>
      <td></td>
      <td></td>
      <td>12.87</td>
      <td>-85.21</td>
      <td>14721</td>
      <td>confirmed</td>
      <td>2022-07-06 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>897</th>
      <td>Nicaragua</td>
      <td>NI</td>
      <td></td>
      <td></td>
      <td></td>
      <td>12.87</td>
      <td>-85.21</td>
      <td>14721</td>
      <td>confirmed</td>
      <td>2022-07-07 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>898</th>
      <td>Nicaragua</td>
      <td>NI</td>
      <td></td>
      <td></td>
      <td></td>
      <td>12.87</td>
      <td>-85.21</td>
      <td>14721</td>
      <td>confirmed</td>
      <td>2022-07-08 00:00:00+00:00</td>
    </tr>
  </tbody>
</table>
<p>899 rows × 10 columns</p>
</div>
```
:::
:::

::: {.cell .code execution_count="43"}
``` {.python}
url_rt_gt = 'https://api.covid19api.com/country/guatemala/status/confirmed/live'
df_rt_gt = pd.read_json(url_rt_gt)
df_rt_gt
```

::: {.output .execute_result execution_count="43"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>CountryCode</th>
      <th>Province</th>
      <th>City</th>
      <th>CityCode</th>
      <th>Lat</th>
      <th>Lon</th>
      <th>Cases</th>
      <th>Status</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Guatemala</td>
      <td>GT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.78</td>
      <td>-90.23</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-22 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Guatemala</td>
      <td>GT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.78</td>
      <td>-90.23</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-23 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Guatemala</td>
      <td>GT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.78</td>
      <td>-90.23</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-24 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Guatemala</td>
      <td>GT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.78</td>
      <td>-90.23</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-25 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Guatemala</td>
      <td>GT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.78</td>
      <td>-90.23</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-26 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>894</th>
      <td>Guatemala</td>
      <td>GT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.78</td>
      <td>-90.23</td>
      <td>921146</td>
      <td>confirmed</td>
      <td>2022-07-04 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>895</th>
      <td>Guatemala</td>
      <td>GT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.78</td>
      <td>-90.23</td>
      <td>922340</td>
      <td>confirmed</td>
      <td>2022-07-05 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>896</th>
      <td>Guatemala</td>
      <td>GT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.78</td>
      <td>-90.23</td>
      <td>927473</td>
      <td>confirmed</td>
      <td>2022-07-06 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>897</th>
      <td>Guatemala</td>
      <td>GT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.78</td>
      <td>-90.23</td>
      <td>933259</td>
      <td>confirmed</td>
      <td>2022-07-07 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>898</th>
      <td>Guatemala</td>
      <td>GT</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.78</td>
      <td>-90.23</td>
      <td>933259</td>
      <td>confirmed</td>
      <td>2022-07-08 00:00:00+00:00</td>
    </tr>
  </tbody>
</table>
<p>899 rows × 10 columns</p>
</div>
```
:::
:::

::: {.cell .code execution_count="44"}
``` {.python}
url_rt_sv = 'https://api.covid19api.com/country/el-salvador/status/confirmed/live'
df_rt_sv = pd.read_json(url_rt_sv)
df_rt_sv
```

::: {.output .execute_result execution_count="44"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>CountryCode</th>
      <th>Province</th>
      <th>City</th>
      <th>CityCode</th>
      <th>Lat</th>
      <th>Lon</th>
      <th>Cases</th>
      <th>Status</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>El Salvador</td>
      <td>SV</td>
      <td></td>
      <td></td>
      <td></td>
      <td>13.79</td>
      <td>-88.9</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-22 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>1</th>
      <td>El Salvador</td>
      <td>SV</td>
      <td></td>
      <td></td>
      <td></td>
      <td>13.79</td>
      <td>-88.9</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-23 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>El Salvador</td>
      <td>SV</td>
      <td></td>
      <td></td>
      <td></td>
      <td>13.79</td>
      <td>-88.9</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-24 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>3</th>
      <td>El Salvador</td>
      <td>SV</td>
      <td></td>
      <td></td>
      <td></td>
      <td>13.79</td>
      <td>-88.9</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-25 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>El Salvador</td>
      <td>SV</td>
      <td></td>
      <td></td>
      <td></td>
      <td>13.79</td>
      <td>-88.9</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-26 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>894</th>
      <td>El Salvador</td>
      <td>SV</td>
      <td></td>
      <td></td>
      <td></td>
      <td>13.79</td>
      <td>-88.9</td>
      <td>169646</td>
      <td>confirmed</td>
      <td>2022-07-04 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>895</th>
      <td>El Salvador</td>
      <td>SV</td>
      <td></td>
      <td></td>
      <td></td>
      <td>13.79</td>
      <td>-88.9</td>
      <td>169646</td>
      <td>confirmed</td>
      <td>2022-07-05 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>896</th>
      <td>El Salvador</td>
      <td>SV</td>
      <td></td>
      <td></td>
      <td></td>
      <td>13.79</td>
      <td>-88.9</td>
      <td>169646</td>
      <td>confirmed</td>
      <td>2022-07-06 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>897</th>
      <td>El Salvador</td>
      <td>SV</td>
      <td></td>
      <td></td>
      <td></td>
      <td>13.79</td>
      <td>-88.9</td>
      <td>169646</td>
      <td>confirmed</td>
      <td>2022-07-07 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>898</th>
      <td>El Salvador</td>
      <td>SV</td>
      <td></td>
      <td></td>
      <td></td>
      <td>13.79</td>
      <td>-88.9</td>
      <td>169646</td>
      <td>confirmed</td>
      <td>2022-07-08 00:00:00+00:00</td>
    </tr>
  </tbody>
</table>
<p>899 rows × 10 columns</p>
</div>
```
:::
:::

::: {.cell .code execution_count="45"}
``` {.python}
url_rt_hn = 'https://api.covid19api.com/country/honduras/status/confirmed/live'
df_rt_hn = pd.read_json(url_rt_hn)
df_rt_hn
```

::: {.output .execute_result execution_count="45"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Country</th>
      <th>CountryCode</th>
      <th>Province</th>
      <th>City</th>
      <th>CityCode</th>
      <th>Lat</th>
      <th>Lon</th>
      <th>Cases</th>
      <th>Status</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Honduras</td>
      <td>HN</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.2</td>
      <td>-86.24</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-22 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Honduras</td>
      <td>HN</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.2</td>
      <td>-86.24</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-23 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Honduras</td>
      <td>HN</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.2</td>
      <td>-86.24</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-24 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Honduras</td>
      <td>HN</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.2</td>
      <td>-86.24</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-25 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Honduras</td>
      <td>HN</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.2</td>
      <td>-86.24</td>
      <td>0</td>
      <td>confirmed</td>
      <td>2020-01-26 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>894</th>
      <td>Honduras</td>
      <td>HN</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.2</td>
      <td>-86.24</td>
      <td>427718</td>
      <td>confirmed</td>
      <td>2022-07-04 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>895</th>
      <td>Honduras</td>
      <td>HN</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.2</td>
      <td>-86.24</td>
      <td>427718</td>
      <td>confirmed</td>
      <td>2022-07-05 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>896</th>
      <td>Honduras</td>
      <td>HN</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.2</td>
      <td>-86.24</td>
      <td>427718</td>
      <td>confirmed</td>
      <td>2022-07-06 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>897</th>
      <td>Honduras</td>
      <td>HN</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.2</td>
      <td>-86.24</td>
      <td>427718</td>
      <td>confirmed</td>
      <td>2022-07-07 00:00:00+00:00</td>
    </tr>
    <tr>
      <th>898</th>
      <td>Honduras</td>
      <td>HN</td>
      <td></td>
      <td></td>
      <td></td>
      <td>15.2</td>
      <td>-86.24</td>
      <td>427718</td>
      <td>confirmed</td>
      <td>2022-07-08 00:00:00+00:00</td>
    </tr>
  </tbody>
</table>
<p>899 rows × 10 columns</p>
</div>
```
:::
:::

::: {.cell .markdown}
Para cada una de las tablas de los países de Centroamérica selecciono
los casos por fecha y ploteo.
:::

::: {.cell .code execution_count="52"}
``` {.python}
casos_pa = df_rt_pa.set_index('Date')['Cases']
casos_pa.plot(title="Casos de COVID-19 en Panamá")
```

::: {.output .execute_result execution_count="52"}
    <AxesSubplot:title={'center':'Casos de COVID-19 en Panamá'}, xlabel='Date'>
:::

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/e7a0af5b7b3cac772862aaca5ecaccccb295e9d4.png)
:::
:::

::: {.cell .code execution_count="53"}
``` {.python}
casos_cr = df_rt_cr.set_index('Date')['Cases']
casos_cr.plot(title="Casos de COVID-19 en Costa Rica")
```

::: {.output .execute_result execution_count="53"}
    <AxesSubplot:title={'center':'Casos de COVID-19 en Costa Rica'}, xlabel='Date'>
:::

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/2efd4cf2e201463046744d7a8d9e1b4bd1802fcf.png)
:::
:::

::: {.cell .code execution_count="54"}
``` {.python}
casos_ni = df_rt_ni.set_index('Date')['Cases']
casos_ni.plot(title="Casos de COVID-19 en Nicaragua")
```

::: {.output .execute_result execution_count="54"}
    <AxesSubplot:title={'center':'Casos de COVID-19 en Nicaragua'}, xlabel='Date'>
:::

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/1aec8a148cca09cfa8cbdfe18554dd01c1a02f57.png)
:::
:::

::: {.cell .code execution_count="55"}
``` {.python}
casos_gt = df_rt_gt.set_index('Date')['Cases']
casos_gt.plot(title="Casos de COVID-19 en Guatemala")
```

::: {.output .execute_result execution_count="55"}
    <AxesSubplot:title={'center':'Casos de COVID-19 en Guatemala'}, xlabel='Date'>
:::

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/c6afdc0a219a5727c5b82ff3cb50c5867421c78f.png)
:::
:::

::: {.cell .code execution_count="56"}
``` {.python}
casos_sv = df_rt_sv.set_index('Date')['Cases']
casos_sv.plot(title="Casos de COVID-19 en El Salvador")
```

::: {.output .execute_result execution_count="56"}
    <AxesSubplot:title={'center':'Casos de COVID-19 en El Salvador'}, xlabel='Date'>
:::

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/3d8a497840d374a56c4a8e8e82ea0a5ab7c536ea.png)
:::
:::

::: {.cell .code execution_count="57"}
``` {.python}
casos_hn = df_rt_hn.set_index('Date')['Cases']
casos_hn.plot(title="Casos de COVID-19 en Honduras")
```

::: {.output .execute_result execution_count="57"}
    <AxesSubplot:title={'center':'Casos de COVID-19 en Honduras'}, xlabel='Date'>
:::

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/ee1200a36e03522a36035ec2acaa6e904ed50a63.png)
:::
:::

::: {.cell .markdown}
## Concatenar todos los países de Centroamérica
:::

::: {.cell .markdown}
Ahora que tengo las gráficas, concateno todas las tablas y le coloco el
nombre por cada uno de los países a los que pertenecen las columnas.
:::

::: {.cell .code execution_count="58"}
``` {.python}
casos_pa_cr_ni_gt_sv_hn = pd.concat([casos_pa,casos_cr,casos_ni,casos_gt,casos_sv,casos_hn],axis=1)
casos_pa_cr_ni_gt_sv_hn.columns= ['Panamá','Costa Rica', 'Nicaragua', 'Guatemala', 'El Salvador', 'Honduras']
casos_pa_cr_ni_gt_sv_hn
```

::: {.output .execute_result execution_count="58"}
```{=html}
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Panamá</th>
      <th>Costa Rica</th>
      <th>Nicaragua</th>
      <th>Guatemala</th>
      <th>El Salvador</th>
      <th>Honduras</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2020-01-22 00:00:00+00:00</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-23 00:00:00+00:00</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-24 00:00:00+00:00</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-25 00:00:00+00:00</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2020-01-26 00:00:00+00:00</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2022-07-04 00:00:00+00:00</th>
      <td>925254</td>
      <td>904934</td>
      <td>14690</td>
      <td>921146</td>
      <td>169646</td>
      <td>427718</td>
    </tr>
    <tr>
      <th>2022-07-05 00:00:00+00:00</th>
      <td>925254</td>
      <td>904934</td>
      <td>14690</td>
      <td>922340</td>
      <td>169646</td>
      <td>427718</td>
    </tr>
    <tr>
      <th>2022-07-06 00:00:00+00:00</th>
      <td>925254</td>
      <td>904934</td>
      <td>14721</td>
      <td>927473</td>
      <td>169646</td>
      <td>427718</td>
    </tr>
    <tr>
      <th>2022-07-07 00:00:00+00:00</th>
      <td>925254</td>
      <td>904934</td>
      <td>14721</td>
      <td>933259</td>
      <td>169646</td>
      <td>427718</td>
    </tr>
    <tr>
      <th>2022-07-08 00:00:00+00:00</th>
      <td>925254</td>
      <td>904934</td>
      <td>14721</td>
      <td>933259</td>
      <td>169646</td>
      <td>427718</td>
    </tr>
  </tbody>
</table>
<p>899 rows × 6 columns</p>
</div>
```
:::
:::

::: {.cell .markdown}
Ahora ploteo para visualizar la comparación en la gráfica.
:::

::: {.cell .code execution_count="61"}
``` {.python}
casos_pa_cr_ni_gt_sv_hn.plot(title="Evolución de los casos de COVID-19 en Centroamérica")
```

::: {.output .execute_result execution_count="61"}
    <AxesSubplot:title={'center':'Evolución de los casos de COVID-19 en Centroamérica'}, xlabel='Date'>
:::

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/b864f5364a23654c53b3cceb533cf89080edcad7.png)
:::
:::

::: {.cell .markdown}
### Exportar la tabla de la comparación en Centroamérica

Ahora exporto la tabla en CSV y la gráfica en formato SVG.
:::

::: {.cell .code execution_count="62"}
``` {.python}
casos_pa_cr_ni_gt_sv_hn.to_csv('casos_pa_cr_ni_gt_sv_hn.csv')
%ls
```

::: {.output .stream .stdout}
     Volume in drive C is Windows-SSD
     Volume Serial Number is 3E46-6E69

     Directory of C:\Users\Evole\gcuevasbenitez-web

    07/08/2022  08:23 PM    <DIR>          .
    07/08/2022  08:23 PM    <DIR>          ..
    07/01/2022  09:34 PM    <DIR>          .ipynb_checkpoints
    06/26/2022  11:52 AM             3,592 ad1.md
    06/27/2022  10:26 PM             3,751 ad2.md
    06/26/2022  01:41 PM            13,640 ad3.ipynb
    06/26/2022  06:39 PM           136,123 adtres.ipynb
    06/27/2022  10:13 PM           115,058 adtres.md
    06/26/2022  06:40 PM           136,123 adtres-Copy1.ipynb
    07/08/2022  08:22 PM           438,489 api-covid-pandas.ipynb
    07/08/2022  08:23 PM            56,679 casos_pa_cr_ni_gt_sv_hn.csv
    07/08/2022  08:05 PM            38,677 pa_vs_cr.csv
    07/08/2022  08:06 PM            13,689 pa_vs_es.png
    07/08/2022  08:07 PM            41,471 pa_vs_es.svg
    06/27/2022  10:26 PM               480 README.md
                  12 File(s)        997,772 bytes
                   3 Dir(s)  50,198,749,184 bytes free
:::
:::

::: {.cell .code execution_count="63"}
``` {.python}
casos_pa_cr_ni_gt_sv_hn.plot(title="Centroamérica")
plt.savefig("casos_pa_cr_ni_gt_sv_hn.svg", format="svg")
%ls
```

::: {.output .stream .stdout}
     Volume in drive C is Windows-SSD
     Volume Serial Number is 3E46-6E69

     Directory of C:\Users\Evole\gcuevasbenitez-web

    07/08/2022  08:23 PM    <DIR>          .
    07/08/2022  08:23 PM    <DIR>          ..
    07/01/2022  09:34 PM    <DIR>          .ipynb_checkpoints
    06/26/2022  11:52 AM             3,592 ad1.md
    06/27/2022  10:26 PM             3,751 ad2.md
    06/26/2022  01:41 PM            13,640 ad3.ipynb
    06/26/2022  06:39 PM           136,123 adtres.ipynb
    06/27/2022  10:13 PM           115,058 adtres.md
    06/26/2022  06:40 PM           136,123 adtres-Copy1.ipynb
    07/08/2022  08:22 PM           438,489 api-covid-pandas.ipynb
    07/08/2022  08:23 PM            56,679 casos_pa_cr_ni_gt_sv_hn.csv
    07/08/2022  08:23 PM            69,782 casos_pa_cr_ni_gt_sv_hn.svg
    07/08/2022  08:05 PM            38,677 pa_vs_cr.csv
    07/08/2022  08:06 PM            13,689 pa_vs_es.png
    07/08/2022  08:07 PM            41,471 pa_vs_es.svg
    06/27/2022  10:26 PM               480 README.md
                  13 File(s)      1,067,554 bytes
                   3 Dir(s)  50,198,110,208 bytes free
:::

::: {.output .display_data}
![](vertopal_bfd34b3cd713491ebce284a473a02bfb/873debbe6c2e263d970fc1752e991123e8061718.png)
:::
:::
