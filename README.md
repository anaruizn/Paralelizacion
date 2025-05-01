# 📌 Paralelización 
Se utiliza el paquete multiprocessing para reducir el tiempo de cómputo de un algoritmo de Metrópolis que calcula el comportamiento de cierta cantidad de fotones al interacuar con un átomo y una cadena de tres átomos. 

# 🧩 ¿Qué hace el proyecto?
Implementa el algoritmo de Metrópolis para simular la emisión fotoeléctrica en distintos metales al ser iluminados por fotones con diversas energías dentro de un rango de frecuencias definido. Se utilizaron las funciones de trabajo de cinco metales (aluminio, cobre, oro, plata y hierro), considerando dos configuraciones: un solo átomo y una cadena unidimensional de tres átomos. La energía de los fotones incidentes se modeló como:

$$E = hν$$.

Se incorpora la estadística de Fermi-Dirac para describir la distribución de energías de los electrones. Así, la probabilidad de encontrar un electrón con energía $E$ está dada por:

$$f(E)=\frac{1}{e^{(E-E_F)/k_{B}T}+1}$$ ,

donde $E_F$ es la energía de Fermi, $k_{B}$ es la constante de Boltzmann y $T$ es la temperatura.

La emisión ocurre únicamente si se cumple la condición:

$$E_{fotón}+E_{electrón}>\phi$$

donde $\phi$ es la función de trabajo del material. Los valores de $\phi$ se toman de los reportados en la literatura para cada material.

De este modo, cada fotón incidente puede:

* Emitir un electrón si la energía total supera $\phi$

* Ser reflejado si hay electrón disponible pero no hay energía suficiente.

* Ser transmitido si no hay electrón disponible.

Para el caso particular de 3 átomos se tiene en cuenta además, si el fotón interactua o no con algún átomo. En este caso, si el fotón no interactua se contará como transmitido.

La simulación se realiza para un rango de frecuencias y permite estudiar el comportamiento estadístico de la emisión fotoeléctrica bajo condiciones controladas.

# 🧠 ¿Por qué el proyecto es útil? 

Simulaciones que requieren millones de iteraciones para cubrir múltiples frecuencias y configuraciones pueden volverse costosas en tiempo de ejecución. Por eso, este proyecto implementa técnicas de paralelización utilizando el módulo multiprocessing de Python para distribuir las tareas entre varios núcleos del procesador. Esto permite: reducir significativamente el tiempo de simulación, escalar fácilmente a configuraciones más grandes y explorar de forma eficiente un mayor número de parámetros físicos. Este proyecto permite utilizar multiprocessing para estudiar y comparar cómo interactúan los fotones con átomos individuales frente a configuraciones más complejas, como cadenas unidimensionales de átomos. Al modificar parámetros físicos como la energía de Fermi, la función de trabajo o la distribución electrónica, es posible simular materiales más realistas y explorar cómo estas propiedades afectan la emisión fotoeléctrica.

# 🚀 ¿Cómo pueden comenzar los usuarios con el proyecto?

1. Defina las constantes involucradas en el proceso de fotoemisión, como por ejemplo, la constante de Planck y la velocidad de la luz.
2. Asegúrese de utilizar las unidades adecuadas y consistentes a lo largo de todo el cálculo para obtener resultados precisos.
3. Fije la temperatura del sistema y la energía de Fermi según su propósito.
4. Defina el número de iteraciones que quiere sean ejecutadas.
5. Definia el rango de energía de los fotones incidentes y la cantidad de fotones que interactuarán con el/los átomo/s.
6. Ejecute el código.

# 🧰 ¿Dónde pueden recibir ayuda los usuarios con tu proyecto?

Si requiere ayuda con el proyecto o tiene dudas al respecto, puede escribir al e-mail: ana.ruizn@udea.edu.co

# 🤝 ¿Quién mantiene y contribuye con el proyecto?
Ana Luz Ruiz Noriega





