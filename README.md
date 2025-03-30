# SQL-
# Carga la extension para usar en Jupyter notebook
!pip install ipython-sql 
# Carga la extension para usar en Jupyter notebook
%load_ext sql
# Guarda un conector a la base de dato en una variable
con = sqlite3.connect("BBDD.db") 
# Guarda en una variable el cursor(objeto) que puede hacer ejecuciones interactuando con la base de datos
cur = con.cursor()
# Se usa para llamar con ese atajo(%sql) a la base de datos
%sql sqlite:///BBDD.db 


# Ejemplo carga de datos
df = pandas.read_csv('https://data.cityofchicago.org/resource/jcxq-k9xf.csv')
# carga el dataframe en la base de datos
df.to_sql("chicago_socioeconomic_data", con, if_exists='replace', index=False,method="multi") 

# Install the 'ipython-sql' and 'prettytable' libraries using pip
!pip install ipython-sql prettytable

# Import the 'prettytable' library, which is used to display data in a formatted table
import prettytable

# Set the default display format for prettytable to 'DEFAULT' (i.e., a simple table format)
prettytable.DEFAULT = 'DEFAULT'
