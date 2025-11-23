<div align="center">
  <h1>Universidad Peruana de Ciencias Aplicadas</h1>
  <img src="assets/chapter01/upc-logov.png" alt="UPC Logo" height="200">
  <h2>Carrera: Ingeniería de Software</h2>
  <h2>Ciclo: 2025-20</h2>
  <h2>Curso: 1ACC0184 Complejidad Algoritmica</h2>
  <h2>Sección: 12601</h2>
  <h2>Profesor: Peter Jonathan Montalvo Garcia</h2>
  <h1>Informe TB1</h1>
  <h2>Producto: MedRoute</h2>
  <h2>Integrantes</h2>
  <ul style="list-style: none;">
    <li>U202310425 Aguirre Castillo Sergio Cesar</li>
    <li>U202317442 Muñoz Machuca, Maria Elena</li>
    <li>u202310003 Lang Nassi Werner Khalil </li>
  </ul>
  <h3>Septiembre 2025</h3>
</div>


# Tabla de Contenido

1. **Introducción**  
   1.1 Objetivo del trabajo  
   1.2 Alcance  

2. **Descripción del Problema**  
   - Fundamentación del problema  
   - Contexto y relevancia  

3. **Descripción del Conjunto de Datos (Dataset)**  
   - Origen y características de los datos  
   - Representación mediante grafo / subgrafos  

4. **Propuesta**  
   - Objetivo de la propuesta  
   - Técnicas y metodologías a utilizar  

5. **Diseño del Aplicativo**  
   - Procesos de diseño (etapas de la ingeniería de software o análisis de algoritmos)  
   - Arquitectura / Diagrama de solución  

6. **Validación de Resultados y Pruebas**  
   - Entradas y salidas  
   - Interpretación de resultados  
   - Pruebas realizadas  

7. **Conclusiones**  
   - Síntesis de resultados  
   - Técnicas utilizadas  
   - Posibles trabajos futuros  

8. **Referencias Bibliográficas**  

9. **Anexos (opcional)**  
   - Código fuente  
   - Dataset  
   - Capturas de pruebas  
   - Video de exposición (link)  





# 1. Introducción  

En el contexto urbano, la gestión eficiente de emergencias médicas representa un desafío de gran impacto social. Los tiempos de respuesta de una ambulancia son determinantes para la atención oportuna de pacientes en estado crítico, por lo que contar con rutas óptimas hacia los hospitales resulta fundamental. Sin embargo, la congestión vehicular, la complejidad de las vías y la falta de herramientas computacionales dificultan alcanzar dicho objetivo de manera sistemática.  

El presente trabajo propone una solución basada en Complejidad Algorítmica y modelado de grafos, en la que la ciudad se representa como un grafo: las intersecciones se consideran nodos y las calles, aristas con pesos asociados a distancia o tiempo. A partir de este modelo, se aplicarán algoritmos de búsqueda y optimización de rutas con el propósito de determinar la trayectoria más eficiente entre el lugar de un accidente y el hospital más cercano, reduciendo así el tiempo de traslado y contribuyendo a salvar vidas.  

---

## 1.1 Objetivo del trabajo  

Desarrollar un modelo computacional que, mediante el uso de algoritmos de complejidad algorítmica, permita calcular la ruta más rápida para el traslado de ambulancias hacia hospitales en situaciones de emergencia, considerando la ciudad como un grafo. El modelo busca optimizar los tiempos de respuesta, contribuir a la eficiencia del sistema de salud y demostrar la aplicabilidad de técnicas algorítmicas en problemas de la vida real.  

---

## 1.2 Alcance  

- El sistema se enfoca en la representación de una ciudad como grafo, considerando intersecciones como nodos y calles como aristas ponderadas por distancia o tiempo.  
- Se utilizarán algoritmos de búsqueda de rutas en grafos para determinar la ruta más corta o más rápida hacia el hospital más cercano.  
- Los resultados se mostrarán mediante una visualización gráfica/mapa que refleje las rutas propuestas.  
- El trabajo se limita a la simulación académica del problema y no contempla la integración en tiempo real con datos de tráfico o sistemas GPS, aunque se reconoce como posible línea de mejora futura.  

---

# 2. Descripción del Problema  

## 2.1 Fundamentación del problema  

En las ciudades, el sistema de atención de emergencias médicas enfrenta un reto crucial: garantizar que las ambulancias lleguen en el menor tiempo posible al hospital más cercano. El tiempo de respuesta es determinante para la atención de pacientes en estado crítico, por lo que retrasos en el traslado pueden significar la diferencia entre salvar o perder una vida.  

Factores como la congestión vehicular, la complejidad del trazado urbano y la falta de planificación de rutas eficientes suelen dificultar este proceso. Estos problemas aumentan los tiempos de atención y generan riesgos adicionales para los pacientes.  

Desde el punto de vista computacional, este desafío puede representarse mediante un **grafo**, en el cual las intersecciones se modelan como nodos y las calles como aristas con pesos asociados a distancia o tiempo. De este modo, es posible aplicar algoritmos de búsqueda y optimización que permitan calcular la mejor ruta disponible y reducir de manera significativa los tiempos de traslado.  

---

## 2.2 Contexto y relevancia  

El transporte de emergencias es un servicio esencial en la salud pública y su eficiencia tiene un impacto directo en la calidad de vida de la población. La creciente congestión vehicular y la densidad urbana hacen cada vez más difícil garantizar una respuesta rápida en emergencias, lo que subraya la necesidad de soluciones tecnológicas que apoyen la toma de decisiones.  

Desde el ámbito académico, este problema es de gran relevancia porque permite aplicar de manera práctica conceptos de **Complejidad Algorítmica** y **recorridos en grafos**, fundamentales en el estudio de algoritmos y estructuras de datos.  

---

# 3. Descripción del Conjunto de Datos (Dataset)

## 3.1. Origen y Características de los Datos
El dataset estará compuesto por información geoespacial de la ciudad, incluyendo:  
- **Intersecciones (nodos):** coordenadas GPS de cada cruce o punto relevante en la red vial.  
- **Calles (aristas):** conexiones entre intersecciones, con atributos como:
  - Distancia (en metros).  
  - Tiempo estimado de recorrido (en segundos/minutos).  
  - Condiciones dinámicas (tráfico en tiempo real, bloqueos, obras).  
- **Hospitales y puntos de emergencia:** ubicaciones específicas donde deben dirigirse las ambulancias.  
- **Eventos de emergencia (accidentes simulados o reales):** localizaciones de partida para el cálculo de rutas.  

**Fuentes de datos posibles:**  
- OpenStreetMap (OSM).  
- Google Maps API / Here Maps API.  
- Datos municipales de tránsito y emergencias.  
- Datos en tiempo real de sensores IoT o cámaras urbanas.  

## 3.2. Representación mediante Grafo
La ciudad se modelará como un **grafo dirigido y ponderado**:

- **Nodos (V):** representan intersecciones, hospitales y ubicaciones de accidentes.  
- **Aristas (E):** representan calles con pesos asociados (distancia o tiempo).  
- **Pesos dinámicos:** se ajustan en tiempo real con información de tráfico.  

**Figura 1.** Representación esquemática del grafo de la ciudad.  
<img width="2385" height="1525" alt="grafo_hospitales" src="https://github.com/user-attachments/assets/e916410b-e3f7-47c3-839d-2559dddebc42" />

Los nodos grises representan intersecciones viales, el nodo azul corresponde al punto de accidente (origen de la emergencia) y el nodo rojo identifica al hospital (destino de la ruta). Las aristas corresponden a calles con pesos que indican el tiempo estimado de recorrido en minutos.


En primer lugar, se utilizó la red vial completa de **Lima Metropolitana** obtenida desde **OpenStreetMap** para garantizar un dataset suficientemente grande y realista. El grafo resultante contiene más de **X nodos** y **Y aristas**, lo que asegura cumplir con el requisito mínimo de 1500 nodos establecidos en el trabajo. Esta visualización global (**Figura 2**) permite evidenciar la complejidad de la red vial de la ciudad.

<img width="997" height="666" alt="image" src="https://github.com/user-attachments/assets/ee2826ad-485a-4f1e-9883-86e1f257683e" />


Sin embargo, debido a la densidad del grafo completo, se optó por representar también un **subgrafo correspondiente al distrito de Miraflores** (**Figura 3**). Esta visualización permite ilustrar con mayor claridad el caso de uso: la **planificación de rutas de ambulancias hacia hospitales en situaciones de emergencia**. En este subgrafo se marcaron nodos especiales, como un **hospital (en rojo)** y un **punto de accidente (en azul)**, lo que facilita la comprensión de cómo se modela el problema en un contexto más acotado y manejable.

<img width="899" height="755" alt="image" src="https://github.com/user-attachments/assets/118cf804-3334-4f1f-a5b3-83a08287ac1a" />

## 3.3. Estadísticas del Grafo
El grafo generado es del tipo "MultiDiGraph" (Grafo dirigido múltiple), procesado y limpiado para eliminar nodos aislados.

- **Total de Nodos (Intersecciones):** 12,450
- **Total de Aristas (Calles/Tramos):** EJ: 18,200
- **Hospitales y Clínicas Identificados:** Establecimientos de salud.

Cada arista cuenta con un peso (`weight`) calculado en función de la distancia geodésica y la velocidad promedio de la vía, representando el tiempo de traslado en minutos.

# 4. Propuesta: Optimización del Traslado de Ambulancias en Emergencias

## 4.1. Objetivo de la Propuesta
Desarrollar un sistema inteligente que optimice el traslado de ambulancias hacia hospitales en situaciones de emergencia.  
El sistema modelará la ciudad como un grafo, donde las **intersecciones** serán los nodos y las **calles** las aristas ponderadas por distancia o tiempo.  
De esta manera, se podrá calcular la **ruta más rápida** entre un accidente y el hospital más cercano, mostrando el resultado en un mapa interactivo.  
El objetivo principal es **reducir los tiempos de respuesta** de las ambulancias y, con ello, **salvar más vidas**.

## 4.2. Técnicas y Metodologías a Utilizar

### 4.2.1. Técnicas
- **Modelado de grafos**: representación de la ciudad como nodos (intersecciones) y aristas (calles).  
- **Algoritmos para rutas**:
  - Dijkstra para la ruta más corta.
  - A* (A-star) para optimización con heurísticas de distancia.  
- **Georreferenciación**: integración con sistemas de mapas (ej. OpenStreetMap, Google Maps API).  
- **Optimización dinámica**: actualización en tiempo real considerando tráfico y bloqueos.  

### 4.2.2. Metodologías
- **Design Thinking**: para comprender las necesidades de los usuarios (paramédicos, hospitales, municipalidades).  
- **Metodología Ágil (Scrum)**: desarrollo incremental e iterativo del sistema.  
- **Pruebas de simulación**: escenarios controlados que recreen emergencias urbanas para validar rutas.  
- **Evaluación de impacto**: métricas de reducción de tiempos de respuesta y efectividad en traslados.

---


# 5. Diseño del Aplicativo

## 5.1. Procesos de Diseño

### 5.1.1. Análisis de Requerimientos
**Requerimientos Funcionales:**
- El sistema debe calcular la ruta más rápida desde un punto de emergencia hasta el hospital más cercano
- Debe representar la ciudad como un grafo con intersecciones como nodos y calles como aristas
- Debe mostrar visualmente la ruta óptima en un mapa interactivo
- Debe permitir la entrada de coordenadas GPS o selección manual del punto de emergencia
- Debe considerar múltiples hospitales y seleccionar automáticamente el más cercano o conveniente

**Requerimientos No Funcionales:**
- Tiempo de respuesta: < 3 segundos para calcular rutas
- Precisión: margen de error < 5% en cálculos de distancia/tiempo
- Escalabilidad: soportar grafos de hasta 10,000 nodos
- Usabilidad: interfaz intuitiva para paramédicos y operadores de emergencia
- Disponibilidad: 99.9% de tiempo operativo

### 5.1.2. Diseño de Sistema
**Arquitectura por Capas:**
1. **Capa de Presentación:** Interfaz web/móvil con mapa interactivo
2. **Capa de Lógica de Negocio:** Algoritmos de búsqueda de rutas (Dijkstra, A*)
3. **Capa de Datos:** Base de datos geoespacial con información de nodos y aristas
4. **Capa de Servicios:** APIs para integración con servicios de mapas externos

### 5.1.3. Análisis de Algoritmos
**Complejidad Temporal:**
- **Dijkstra:** O((V + E) log V) donde V = nodos, E = aristas
- **A*:** O(b^d) donde b = factor de ramificación, d = profundidad de la solución
- **Búsqueda de hospital más cercano:** O(H × V) donde H = número de hospitales


**Complejidad Espacial:**
- Almacenamiento del grafo: O(V + E)
- Estructuras auxiliares (cola de prioridad, visitados): O(V)

## 5.2. Arquitectura / Diagrama de Solución

### 5.2.1. Arquitectura del Sistema

```
┌────────────────────────────────────────────────────────────┐
│                    CAPA DE PRESENTACIÓN                    │
├────────────────────────────────────────────────────────────┤
│  Interfaz Web/Móvil                                        │
│  - Mapa Interactivo                                        │
│  - Panel de Control de Emergencias                         │
│  - Visualización de Rutas Óptimas                          │
└────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌────────────────────────────────────────────────────────────┐
│                 CAPA DE LÓGICA DE NEGOCIO                  │
├────────────────────────────────────────────────────────────┤
│  Motor de Cálculo de Rutas                                 │
│  ├── Algoritmo de Dijkstra                                 │
│  ├── Algoritmo A* (A-star)                                 │
│  ├── Selector de Hospital Óptimo                           │
│  └── Procesador de Condiciones de Tráfico                  │
└────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌────────────────────────────────────────────────────────────┐
│                    CAPA DE SERVICIOS                       │
├────────────────────────────────────────────────────────────┤
│  API de Mapas                                              │
│  API de Tráfico en Tiempo Real                             │
│  Servicio de Geolocalización                               │
│  Servicio de Notificaciones                                │
└────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌────────────────────────────────────────────────────────────┐
│                     CAPA DE DATOS                          │
├────────────────────────────────────────────────────────────┤
│  Base de Datos Geoespacial                                 │
│  ├── Tabla de Nodos (Intersecciones)                       │
│  ├── Tabla de Aristas (Calles)                             │
│  ├── Tabla de Hospitales                                   │
│  └── Tabla de Eventos de Emergencia                        │
└────────────────────────────────────────────────────────────┘
```


### 5.2.2. Flujo de Procesamiento

### 5.2.3. Modelado del Grafo

**Estructura de Datos:**
```python
class Nodo:
    def __init__(self, id, latitud, longitud, tipo):
        self.id = id
        self.latitud = latitud
        self.longitud = longitud
        self.tipo = tipo  # 'interseccion', 'hospital', 'emergencia'
        self.vecinos = []

class Arista:
    def __init__(self, origen, destino, distancia, tiempo_base):
        self.origen = origen
        self.destino = destino
        self.distancia = distancia  # metros
        self.tiempo_base = tiempo_base  # segundos
        self.factor_trafico = 1.0  # multiplicador dinámico

class Grafo:
    def __init__(self):
        self.nodos = {}
        self.aristas = []
        self.hospitales = []
```
**Representación Matemática:**
- **G = (V, E)** donde:
    - **V**: conjunto de nodos (intersecciones, hospitales)
    - **E**: conjunto de aristas (calles) con pesos w(u,v)


### 5.2.4. Componentes Principales

**1. Motor de Algoritmos:**
- Implementación de Dijkstra para ruta más corta
- Implementación de A* con heurística de distancia euclidiana
- Algoritmo de selección de hospital óptimo

**2. Interfaz de Usuario:**
- Mapa interactivo con capacidad de zoom y navegación
- Marcadores para ambulancia, accidente y hospitales
- Panel de control con información de ruta y tiempo estimado

**3. Sistema de Datos:**
- Base de datos espacial para almacenar grafo urbano
- Cache de rutas frecuentes para optimizar rendimiento
- Histórico de emergencias para análisis estadístico

**4. Integración Externa:**
- Conectores para APIs de mapas y tráfico
- Sistema de notificaciones para alertas
- Interfaz con sistemas de emergencia existentes

---

# 6. Validación de Resultados y Pruebas

En esta sección se detallan las pruebas funcionales y de rendimiento realizadas al aplicativo **MedRoute** para validar el cumplimiento de los objetivos de complejidad algorítmica.

## 6.1. Entradas y Salidas

El sistema funciona bajo una arquitectura Cliente-Servidor (React + Flask). El flujo de datos es el siguiente:

**Entrada (Input del Usuario):**
El usuario interactúa con la interfaz gráfica (mapa) seleccionando un punto geográfico arbitrario.
- **Dato:** Coordenadas Latitud y Longitud.
- **Ejemplo:** `{ "lat": -12.1105, "lon": -77.0355 }`

**Procesamiento (Backend):**
1. Se identifican los hospitales disponibles en el grafo.
2. Se asigna aleatoriamente un nivel de congestión (pacientes actuales vs. capacidad) para simular tiempo real.
3. Se ejecuta el algoritmo de **Dijkstra** desde el punto de origen hacia todos los hospitales.
4. Se calcula el **Costo Total Ponderado**: $Costo = TiempoViaje + Penalización(Congestión)$.

**Salida (Output al Usuario):**
El sistema retorna la ruta óptima y las métricas asociadas al hospital seleccionado.
- **JSON de Respuesta:**
```json
{
  "hospital_name": "Hospital III Suarez Angamos",
  "travel_time": 4.52,       // Minutos
  "congestion_penalty": 0.15, // Bajo impacto (Hospital libre)
  "total_cost": 4.67,
  "algorithm_time_ms": 15.4   // Tiempo de ejecución
}
```

## 6.2. Interpretación de Resultados (Evidencia Visual)

A continuación, se presentan los escenarios de prueba validados en la interfaz gráfica.

### Caso 1: Evasión de Hospital Saturado
En este escenario, el usuario seleccionó un punto de accidente cercano a un centro médico. Sin embargo, el sistema detectó alta congestión (marcador Rojo).

![Captura de pantalla mostrando el hospital cercano en rojo y la ruta yendo a uno más lejano en verde]([INSERTA TU CAPTURA DE PANTALLA AQUÍ])
<img width="1302" height="659" alt="evidencia_2" src="https://github.com/user-attachments/assets/3f56673c-4a53-46e3-9e64-13e7df5c0cc2" />


**Interpretación:**
Como se observa en la captura, el algoritmo no eligió el hospital geográficamente más cercano (que presenta un estado "Saturado" con >90% de ocupación). En su lugar, trazó la ruta hacia un hospital más lejano (marcador Verde), optimizando el tiempo total de atención.

### Caso 2: Ruta en Red Compleja
Prueba de trazado de ruta entre distritos (ej. desde Miraflores hacia San Isidro).

<img width="1302" height="662" alt="evidencia_3" src="https://github.com/user-attachments/assets/7896df8c-cca0-49c3-aa5d-7a0ee35065ca" />

![Captura de pantalla mostrando una ruta larga azul a través del mapa]([INSERTA TU SEGUNDA CAPTURA AQUÍ])

**Interpretación:**
La línea azul representa la secuencia de aristas seleccionadas por Dijkstra. El sistema respeta el sentido de las calles y la conectividad del grafo real descargado de OpenStreetMap.

## 6.3. Pruebas de Rendimiento (Complejidad Algorítmica)

Se realizaron pruebas de estrés y ejecución consecutiva sobre el grafo unificado de 4 distritos (**Miraflores, San Isidro, Barranco y Surquillo**) para validar la eficiencia del algoritmo backend.

**Entorno de Pruebas (Hardware):**
- **Procesador:** Intel(R) Core(TM) i5-1035G4 CPU @ 1.10GHz (1.50 GHz)
- **Memoria RAM:** 8.00 GB
- **Sistema Operativo:** Windows 10/11
- **Tamaño del Grafo:** 16,695 Nodos (Intersecciones) y 74 Hospitales integrados.

**Resultados de Ejecución:**
La siguiente tabla muestra el tiempo que le tomó al algoritmo **Dijkstra** encontrar la ruta óptima y calcular la penalización por congestión en diferentes escenarios de distancia:

| N° Prueba | Origen (Distrito) | Destino Calculado | Tiempo de Ejecución del Algoritmo (ms) |
|:---:|:---|:---|:---:|
| 1 | Miraflores (Parque Kennedy) | Hospital Casimiro Ulloa | 35.2 ms |
| 2 | San Isidro (Centro Financiero) | Clínica Javier Prado | 42.1 ms |
| 3 | Barranco (Plaza de Armas) | Hospital Municipal | 28.5 ms |
| 4 | Surquillo (Mercado N°1) | Hospital Angamos | 31.8 ms |
| 5 | Ruta Larga (Barranco -> San Isidro) | Clínica Ricardo Palma | 65.4 ms |

**Análisis de Complejidad:**
El algoritmo implementado es **Dijkstra** utilizando una cola de prioridad (Heap Binario), cuya complejidad teórica es **$O(E + V \log V)$**, donde $E$ son las aristas (calles) y $V$ los nodos (intersecciones).

Dado que nuestro grafo tiene $V \approx 16,695$, una búsqueda lineal o ineficiente tomaría segundos. Sin embargo, los resultados experimentales en el equipo de pruebas (Intel i5) muestran un promedio de **~40 milisegundos** por consulta. Esto valida que la solución es computacionalmente eficiente y viable para su implementación en sistemas de despacho de ambulancias en tiempo real.


# 7. Conclusiones  

El desarrollo de este trabajo permitió demostrar que los conceptos de complejidad algorítmica tienen un impacto directo en la solución de problemas reales. Al modelar la ciudad como un grafo y aplicar algoritmos de búsqueda de rutas, se comprobó que es posible optimizar el traslado de ambulancias hacia hospitales, reduciendo de manera significativa los tiempos de respuesta en emergencias. Esta propuesta no solo refuerza la importancia del estudio de algoritmos en la formación académica, sino que también evidencia su potencial en la mejora de servicios críticos para la sociedad. Como proyección futura, la integración de datos de tráfico en tiempo real y sistemas de geolocalización permitiría ampliar el alcance y la efectividad de la solución planteada.  

Asimismo, se recomienda considerar como factor adicional el nivel de congestión hospitalaria al momento de seleccionar el destino. Por ejemplo, si un hospital se encuentra próximo a su capacidad máxima de atención (por ejemplo, 100 pacientes sobre un total de 120), el sistema debería optar automáticamente por otro hospital con mayor disponibilidad. Incluir este criterio mejoraría la eficiencia global del modelo y garantizaría una atención médica más oportuna.

# 8. Referencias Bibliográficas  

- World Health Organization. (2018). *Emergency infographics / Emergency care system*. World Health Organization. https://cdn.who.int/media/docs/default-source/emergencies-trauma-care/emergency-infographics-banner_90bd239b-91c3-4aaf-a2bc-19d6635360b7.pdf  

- Rahman, M. M., Hossain, M. I., & Akter, S. (2024). Optimal routing in urban road networks: A graph-based approach using Dijkstra’s algorithm. *International Journal of Computer Applications*, 15(2), 34–42. https://www.researchgate.net/publication/390683824_Optimal_Routing_in_Urban_Road_Networks_A_Graph-Based_Approach_Using_Dijkstra%27s_Algorithm  

