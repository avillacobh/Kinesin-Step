
Autores: 

         Nicolás Alejandro Ávila Pérez

         Andrés Felipe Duque Bran

         Andrés Felipe Villacob Hernández

***

## Descripción
Este código se ecuentra escrito en lenguaje C++ y utiliza un algoritmo de Random Walk para simular la difusión de la cabeza de una kinesina. Mediante el uso del modelo de Yao y Zheng se obtiene la distribución del tiempo de primer paso y la dependencia de la velocidad respecto a la concentración de ATP.

***
## Instrucciones.
  1. En la carpeta Codes se encuentran:
  
      * kinesin.cpp
      * kinesin-backwards.cpp

      Dentro de la función main de ambos archivos se llama a la función ``Data_Velocity(F,Nbins)`` la cual crea dos archvivos de texto, ``first_passage_time_Fext=F.txt``, el cual posee los tiempos de primer paso en segundos de 1000 simulaciones, utilizados para hallar la distribución de probabilidad, y ``datosVel_Fext=F.txt`` el cual contiene en su primera columna la concentración de ATP en unidades de uM y la velocidad promedio respectiva en unidades de nm/s en la segunda columna. El código backwards genera estos mismos archivos con la termianción ``...-backwards.txt``. La fuerza ingresada F en la función Data_Velocity se encuentra en unidades de pN. El usuario es libre de modificar esta fuerza o llamar varias veces la función para obtener los datos deseados. Nbins es el número entero de ``bins`` utilizados para la integración numérica y es fijado en 30; no es necesario ni aconsejable modificar este valor, aunque no representará ningún problema, salvo la precisión de los datos obtenidos. 
  
  2. Para compilar el código se recomienda utilizar la API Openmp utilizando la bandera  ``-fopenmp`` de la siguiente forma 

    g++ kinesin.cpp -fopenmp -o kinesin.out
    g++ kinesin-backwards.cpp -fopenmp -o kinesin-backwards.out

    Nota: no es necesario utilizar la bandera, sin embargo, el tiempo de ejecución es mucho más largo pues no paraleliza el proceso. La ejecución del programa con una fuerza externa de 4.5 pN tardó 8 días en completarse utilizando openmp y los recursos del cluster en el nodo 5. Para fuerzas menores el tiempo es mucho más corto; en el caso 1.5 pN tarda alrededor de 10 min.
      
  
  3. Para ejecutar los programa es necesario escribir en la terminal los comandos,

    .\kinesin.out
    .\kinesin-backwards.out
  
    El programa imprimirá en la terminal líneas de texto para informar al usuario la parte del proceso en el cual se encuentra la ejecución.
 
  
*** 

*Este trabajo fue realizado como proyecto para la materia de ``Introducción a la ivestigación teórica`` en la Universidad Nacional 
de Colombia en el semestre 2021-1. 
