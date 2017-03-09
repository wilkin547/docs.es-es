---
title: "Dimensiones de matrices en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "matrices [Visual Basic], dimensiones"
  - "matrices [Visual Basic], rango"
  - "matrices [Visual Basic], rectangulares"
  - "dimensiones, matrices"
  - "rangos, matrices"
  - "matrices rectangulares"
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Dimensiones de matrices en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una *dimensión* es una dirección en la que puede variar la especificación de los elementos de una matriz.  Una matriz que contiene el total de ventas de todos los días del mes tiene una dimensión \(el día del mes\).  Una matriz que contiene el total de ventas por departamento de todos los días del mes tiene dos dimensiones \(el número del departamento y el día del mes\).  El número de dimensiones que tiene una matriz se denomina *rango*.  
  
> [!NOTE]
>  Puede utilizar la propiedad <xref:System.Array.Rank%2A> para determinar cuántas dimensiones tiene una matriz.  
  
## Trabajar con dimensiones  
 Para especificar un elemento de una matriz, proporcione un *índice* o un *subíndice* para cada una de sus dimensiones.  Los elementos son contiguos a lo largo de cada dimensión del índice 0 al índice más alto para esa dimensión.  
  
 Las ilustraciones siguientes muestran la estructura conceptual de matrices con rangos diferentes.  Cada elemento de las ilustraciones muestra los valores de índice que tienen acceso a él.  Por ejemplo, puede tener acceso al primer elemento de la segunda fila de la matriz bidimensional especificando los índices `(1, 0)`.  
  
 ![Diagrama de gráfico de matriz unidimensional](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.png "ArrayExDimOne")  
Matriz unidimensional  
  
 ![Diagrama de gráfico de matriz bidimensional](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")  
Matriz bidimensional  
  
 ![Diagrama de gráfico de matriz tridimensional](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.png "ArrayExDimThree")  
Matriz tridimensional  
  
### Una dimensión  
 Muchas matrices tienen sólo una dimensión, como el número de personas de cada edad.  El único requisito para especificar un elemento es la edad para la que ese elemento contiene el recuento.  Por lo tanto, este tipo de matriz utiliza sólo un índice.  El ejemplo siguiente declara una variable para que contenga una *matriz unidimensional* de recuentos de edad para edades de 0 a 120.  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### Dos dimensiones  
 Algunas matrices tienen dos dimensiones, como el número de oficinas de cada planta de todos los edificios de un campus.  La especificación de un elemento requiere el número del edificio y de la planta, y cada elemento contiene el recuento para esa combinación de edificio y planta.  Por consiguiente, este tipo de matriz utiliza dos índices.  El ejemplo siguiente declara una variable para que contenga una *matriz bidimensional* de recuentos de oficinas para 0 a 40 edificios y 0 a 5 plantas.  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 Una matriz bidimensional también se denomina *matriz rectangular*.  
  
### Tres dimensiones  
 Algunas matrices tienen tres dimensiones, como los valores de un espacio tridimensional.  Este tipo de matriz utiliza tres índices que, en este caso, representan las coordenadas x, y y z del espacio físico.  El ejemplo siguiente declara una variable para que contenga una *matriz tridimensional* de las temperaturas del aire en distintos puntos de un volumen tridimensional.  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### Más de tres dimensiones  
 Aunque una matriz puede tener hasta un máximo de 32 dimensiones, es raro que tenga más de tres.  
  
> [!NOTE]
>  Cuando se agregan dimensiones a una matriz, el espacio total necesario para guardar la matriz aumenta considerablemente; por ello, debe utilizar las matrices multidimensionales con prudencia.  
  
## Uso de dimensiones diferentes  
 Suponga que desea realizar el seguimiento de las cantidades de ventas de todos los días del mes actual.  Es posible que desee declarar una matriz unidimensional con 31 elementos, uno por cada día del mes, tal como muestra el ejemplo siguiente.  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 Ahora, suponga que desea realizar el seguimiento de la misma información no sólo para todos los días del mes sino también para todos los meses del año.  Puede declarar una matriz bidimensional con 12 filas \(para los meses\) y 31 columnas \(para los días\), tal como muestra el ejemplo siguiente.  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 Ahora, suponga que decide mantener la información en la matriz durante más de un año.  Si desea realizar el seguimiento de las cantidades de ventas durante 5 años, puede declarar una matriz tridimensional con 5 capas, 12 filas y 31 columnas, tal como muestra el ejemplo siguiente.  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 Tenga en cuenta que, debido a que un índice varía de 0 a su máximo, las dimensiones de `salesAmounts` se declaran como una menos que la longitud necesaria para esa dimensión.  Observe igualmente que el tamaño de la matriz aumenta con cada nueva dimensión.  Los tres tamaños de los ejemplos anteriores son respectivamente 31, 372 y 1.860 elementos.  
  
> [!NOTE]
>  Puede crear una matriz sin utilizar la instrucción `Dim` o la cláusula `New`.  Por ejemplo, puede llamar al método <xref:System.Array.CreateInstance%2A> u otro componente puede pasar su código a una matriz creada de esta manera.  Este tipo de matriz puede tener un límite inferior distinto de 0.  Siempre puede comprobar el límite inferior de una dimensión con el método <xref:System.Array.GetLowerBound%2A> o la función `LBound`.  
  
## Vea también  
 [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Solucionar problemas de matrices](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)