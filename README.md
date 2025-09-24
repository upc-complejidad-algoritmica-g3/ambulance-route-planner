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
