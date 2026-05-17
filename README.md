# Proyecto-Big-data-Tarea4
# Descripción del Caso de Estudio
Este proyecto implementa un sistema de gestión integral para el restaurante El Rey del Sabor, utilizando MongoDB como base de datos NoSQL.
El sistema está diseñado para almacenar, organizar y analizar información relacionada con:

Clientes: datos personales, historial de pedidos y medios de contacto.

Repartidores: información de entregas, zonas asignadas y desempeño.

Zonas: áreas geográficas de cobertura y distribución.

Productos: platos, bebidas y servicios ofrecidos, con sus precios y categorías.

El propósito principal es optimizar la gestión de pedidos y entregas, garantizando un flujo eficiente desde la toma del pedido hasta la entrega final. Además, permite realizar análisis de datos sobre ventas, desempeño de repartidores y demanda por zonas, apoyando la toma de decisiones administrativas.
# Justificación
La elección de MongoDB para este sistema se justifica por:

1. **Manejo de datos dinámicos**: el restaurante gestiona información que cambia constantemente (clientes, pedidos, productos, zonas).

2. **Flexibilidad y escalabilidad**: MongoDB permite almacenar documentos sin esquemas rígidos, adaptándose fácilmente a nuevos requerimientos del negocio.

3. **Consultas y análisis avanzados**: el sistema permite realizar operaciones como:

-Cálculo de totales y promedios de ventas.

-Identificación de zonas con mayor demanda.

-Evaluación del desempeño de repartidores.

-Control de inventario y productos más vendidos.

4. **Aplicación práctica**: el caso integra conceptos de gestión y análisis de datos en un entorno real, fortaleciendo la eficiencia operativa y la toma de decisiones.

# Estructura de la Base de Datos
Nombre de la Base de Datos:  
RestauranteElReyDelSabor

# Colecciones Implementadas
La base de datos contiene 4 colecciones que organizan toda la información del restaurante:

| Colección     | Documentos | Descripción                                                                 |
|----------------|-------------|------------------------------------------------------------------------------|
| CLIENTES       | 5           | Información de los clientes: nombre, contacto, dirección y historial de pedidos. |
| REPARTIDORES   | 5           | Datos de los repartidores: nombre, zona asignada y cantidad de entregas realizadas. |
| ZONAS          | 4           | Áreas geográficas de cobertura y distribución de pedidos.                     |
| PRODUCTOS      | 96          | Detalle de productos y servicios: nombre, tipo, unidad, precio y disponibilidad. |

##  Detalle de Colecciones

### 1. PRODUCTOS
Almacena información completa de los productos y servicios del restaurante.

- **Campos:**  
  nombre, tipo, unidad_medida, precio_total, item_inventariable, venta_en_negativo, disponibilidad, fecha_creación  

- **Índices:**  
  nombre, tipo, tipo + precio_total  

---

### 2. CLIENTES
Gestiona los datos de los clientes registrados.

- **Campos:**  
  nombre, número_de_contacto, dirección, correo, historial_de_pedido, fecha_registro, activo  

- **Índices:**  
  correo (único), nombre  

---

### 3. REPARTIDORES
Registra la información de los repartidores y sus zonas asignadas.

- **Campos:**  
  nombre, número_de_contacto, zona_asignada, pedidos_entregados, activo  

- **Índices:**  
  zona_asignada, nombre  

---

### 4. ZONAS
Define las áreas geográficas de cobertura del restaurante.

- **Campos:**  
  nombre_zona, descripción, cantidad_pedidos, repartidores_asignados, activo  

- **Índices:**  
  nombre_zona (único)  
