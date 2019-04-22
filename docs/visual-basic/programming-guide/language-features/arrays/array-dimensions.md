---
title: Dimensiones de matrices en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: 0b4e7c9e253f94e1e28700c8669d28799ab69d91
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836940"
---
# <a name="array-dimensions-in-visual-basic"></a>Dimensiones de matrices en Visual Basic
Un *dimensión* es una dirección en la que puede variar la especificación de elementos de una matriz. Una matriz que contiene las ventas totales para cada día del mes tiene una dimensión (el día del mes). Una matriz que contiene las ventas totales por departamento para cada día del mes tiene dos dimensiones (el número de departamento y el día del mes). El número de dimensiones tiene una matriz se llama a su *rango*.  
  
> [!NOTE]
>  Puede usar el <xref:System.Array.Rank%2A> propiedad para determinar cuántas dimensiones tiene de una matriz.  
  
## <a name="working-with-dimensions"></a>Trabajar con dimensiones  
 Especifica un elemento de una matriz al proporcionar un *índice* o *subíndice* para cada uno de sus dimensiones. Los elementos son contiguos en cada dimensión desde el índice 0 hasta el índice más alto para esa dimensión.  
  
 Las ilustraciones siguientes muestran la estructura conceptual de matrices con rangos diferentes. Cada elemento en las ilustraciones muestra los valores de índice que acceden a ellos. Por ejemplo, puede obtener acceso el primer elemento de la segunda fila de la matriz bidimensional especificando los índices `(1, 0)`.  
  
 ![Diagrama que muestra una matriz unidimensional.](./media/array-dimensions/one-dimensional-array.gif)  
  
 ![Diagrama que muestra una matriz bidimensional.](./media/array-dimensions/two-dimensional-array.gif)  
  
 ![Diagrama que muestra una matriz tridimensional.](./media/array-dimensions/three-dimensional-array.gif)  
  
### <a name="one-dimension"></a>Una dimensión  
 Muchas matrices tienen solo una dimensión, como el número de personas de cada edad. El único requisito para especificar un elemento es la edad para los que ese elemento contiene el recuento. Por lo tanto, este tipo de matriz utiliza sólo un índice. En el ejemplo siguiente se declara una variable que contenga un *matriz unidimensional* de edad recuentos de edades de 0 a 120.  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a>Dos dimensiones  
 Algunas matrices tienen dos dimensiones, como el número de oficinas de cada planta de cada edificio en un campus. La especificación de un elemento requiere el número de edificio y piso y cada elemento contiene el recuento para esa combinación de edificio y piso. Por lo tanto, este tipo de matriz utiliza dos índices. En el ejemplo siguiente se declara una variable que contenga un *matriz bidimensional* de recuentos de office, de 0 a 40 edificios y 0 a 5 plantas.  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 Una matriz bidimensional también se denomina un *matriz rectangular*.  
  
### <a name="three-dimensions"></a>Tres dimensiones  
 Algunas matrices tienen tres dimensiones, como los valores de un espacio tridimensional. Este tipo de matriz utiliza tres índices, que se representan en este caso la x, y y las coordenadas z del espacio físico. En el ejemplo siguiente se declara una variable que contenga un *matriz tridimensional* de temperatura del aire en diversos puntos en un volumen tridimensional.  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a>Más de tres dimensiones  
 Aunque una matriz puede tener como máximo 32 dimensiones, es poco habitual tener más de tres.  
  
> [!NOTE]
>  Cuando se agregan dimensiones a una matriz, el almacenamiento total necesario para la matriz aumenta considerablemente, por lo que use las matrices multidimensionales con cuidado.  
  
## <a name="using-different-dimensions"></a>Uso de distintas dimensiones  
 Suponga que desea realizar un seguimiento de los importes de ventas para todos los días del mes actual. Puede declarar una matriz unidimensional con 31 elementos, uno para cada día del mes, como en el ejemplo siguiente se muestra.  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 Ahora suponga que desea realizar un seguimiento de la misma información no solo para todos los días del mes, sino también para todos los meses del año. Puede declarar una matriz bidimensional con 12 filas (para los meses) y 31 columnas (para los días), como se muestra en el ejemplo siguiente.  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 Ahora suponga que decide tiene la matriz contienen información durante más de un año. Si desea realizar un seguimiento de los importes de ventas durante 5 años, podría declarar una matriz tridimensional con 5 capas, 12 filas y 31 columnas, como se muestra en el ejemplo siguiente.  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 Tenga en cuenta que, dado que cada índice varía entre 0 y su valor máximo, cada dimensión de `salesAmounts` se declara como uno menos que la longitud necesaria para esa dimensión. Tenga en cuenta también que el tamaño de la matriz aumenta con cada nueva dimensión. Los tres tamaños en los ejemplos anteriores son 31, 372 y 1.860 elementos respectivamente.  
  
> [!NOTE]
>  Puede crear una matriz sin utilizar el `Dim` instrucción o el `New` cláusula. Por ejemplo, puede llamar a la <xref:System.Array.CreateInstance%2A> método u otro componente puede pasar el código de una matriz creada de esta manera. Dicha matriz puede tener un límite inferior distinto de 0. Siempre puede probar el límite inferior de una dimensión mediante el <xref:System.Array.GetLowerBound%2A> método o la `LBound` función.  
  
## <a name="see-also"></a>Vea también

- [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Solución de problemas de matrices](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
