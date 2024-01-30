- 👋 Hi, I’m @nzjose
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
nzjose/nzjose is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import pandas as pd

# Supongamos que tienes un DataFrame llamado 'df' con los datos de tus pedidos
# Aquí hay un ejemplo de cómo podría ser la estructura de los datos:
data = {
    'Proveedor': ['Proveedor A', 'Proveedor B', 'Proveedor A', 'Proveedor C', 'Proveedor B'],
    'Producto': ['Producto 1', 'Producto 2', 'Producto 3', 'Producto 1', 'Producto 2'],
    'Cantidad': [10, 20, 15, 12, 18],
    'Fecha': ['2024-01-01', '2024-01-02', '2024-01-03', '2024-01-04', '2024-01-05']
}

df = pd.DataFrame(data)

# Generar la tabla dinámica
tabla_dinamica = pd.pivot_table(df, values='Cantidad', index='Proveedor', columns='Producto', aggfunc='sum', fill_value=0)

# Mostrar la tabla dinámica
print("Tabla Dinámica:")
print(tabla_dinamica)

# Solicitar al usuario que ingrese el nombre del proveedor para filtrar la tabla
proveedor_filtro = input("Ingrese el nombre del proveedor para filtrar la tabla: ")

# Filtrar la tabla dinámica por proveedor
if proveedor_filtro in tabla_dinamica.index:
    tabla_filtrada = tabla_dinamica.loc[[proveedor_filtro]]
    print("\nTabla Filtrada para el proveedor", proveedor_filtro, ":")
    print(tabla_filtrada)
else:
    print("\nEl proveedor", proveedor_filtro, "no se encontró en la tabla.")
