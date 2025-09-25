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

Ejemplo de representación en notación de grafo:  


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

  
---








# 7. Conclusiones  

El desarrollo de este trabajo permitió demostrar que los conceptos de complejidad algorítmica tienen un impacto directo en la solución de problemas reales. Al modelar la ciudad como un grafo y aplicar algoritmos de búsqueda de rutas, se comprobó que es posible optimizar el traslado de ambulancias hacia hospitales, reduciendo de manera significativa los tiempos de respuesta en emergencias. Esta propuesta no solo refuerza la importancia del estudio de algoritmos en la formación académica, sino que también evidencia su potencial en la mejora de servicios críticos para la sociedad. Como proyección futura, la integración de datos de tráfico en tiempo real y sistemas de geolocalización permitiría ampliar el alcance y la efectividad de la solución planteada.  


---

# 8. Referencias Bibliográficas  

- World Health Organization. (2018). *Emergency infographics / Emergency care system*. World Health Organization. https://cdn.who.int/media/docs/default-source/emergencies-trauma-care/emergency-infographics-banner_90bd239b-91c3-4aaf-a2bc-19d6635360b7.pdf  

- Rahman, M. M., Hossain, M. I., & Akter, S. (2024). Optimal routing in urban road networks: A graph-based approach using Dijkstra’s algorithm. *International Journal of Computer Applications*, 15(2), 34–42. https://www.researchgate.net/publication/390683824_Optimal_Routing_in_Urban_Road_Networks_A_Graph-Based_Approach_Using_Dijkstra%27s_Algorithm  

