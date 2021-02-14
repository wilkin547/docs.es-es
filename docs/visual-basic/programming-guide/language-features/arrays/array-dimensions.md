---
description: 'Más información acerca de: dimensiones de matriz en Visual Basic'
title: Dimensiones de matriz
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: 055a3efc1410bf80daf3804453adc2c20266733c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100486555"
---
# <a name="array-dimensions-in-visual-basic"></a>Dimensiones de matrices en Visual Basic

Una *dimensión* es una dirección en la que puede variar la especificación de los elementos de una matriz. Una matriz que contiene el total de ventas de cada día del mes tiene una dimensión (el día del mes). Una matriz que contiene el total de ventas por departamento para cada día del mes tiene dos dimensiones (el número de departamento y el día del mes). El número de dimensiones que tiene una matriz se denomina su *rango*.

> [!NOTE]
> Puede utilizar la <xref:System.Array.Rank%2A> propiedad para determinar el número de dimensiones de una matriz.

## <a name="working-with-dimensions"></a>Trabajar con dimensiones

Para especificar un elemento de una matriz, debe proporcionar un *Índice* o *subíndice* para cada una de sus dimensiones. Los elementos son contiguos a lo largo de cada dimensión desde el índice 0 hasta el índice más alto de esa dimensión.

En las ilustraciones siguientes se muestra la estructura conceptual de matrices con distintos rangos. Cada elemento de las ilustraciones muestra los valores de índice que tienen acceso a él. Por ejemplo, puede tener acceso al primer elemento de la segunda fila de la matriz bidimensional especificando los índices `(1, 0)` .

![Diagrama que muestra una matriz unidimensional.](./media/array-dimensions/one-dimensional-array.gif)

![Diagrama que muestra una matriz bidimensional.](./media/array-dimensions/two-dimensional-array.gif)

![Diagrama que muestra una matriz tridimensional.](./media/array-dimensions/three-dimensional-array.gif)

### <a name="one-dimension"></a>Una dimensión

Muchas matrices tienen solo una dimensión, como el número de personas de cada edad. El único requisito para especificar un elemento es la edad para la que ese elemento contiene el recuento. Por lo tanto, una matriz de este tipo solo utiliza un índice. En el ejemplo siguiente se declara una variable para que contenga una *matriz unidimensional* de recuentos de edad de entre 0 y 120.

```vb
Dim ageCounts(120) As UInteger
```

### <a name="two-dimensions"></a>Dos dimensiones

Algunas matrices tienen dos dimensiones, como el número de oficinas en cada piso de cada edificio en un campus. La especificación de un elemento requiere tanto el número de compilación como el piso y cada elemento contiene el recuento de la combinación de edificio y piso. Por lo tanto, una matriz de este tipo utiliza dos índices. En el ejemplo siguiente se declara una variable que contiene una *matriz bidimensional* de recuentos de oficinas, para los edificios 0 a 40 y las plantas 0 a 5.

```vb
Dim officeCounts(40, 5) As Byte
```

Una matriz bidimensional también se denomina *matriz rectangular*.

### <a name="three-dimensions"></a>Tres dimensiones

Algunas matrices tienen tres dimensiones, como los valores en el espacio de tres dimensiones. Este tipo de matriz utiliza tres índices, que en este caso representan las coordenadas x, y y z del espacio físico. En el ejemplo siguiente se declara una variable para que contenga una *matriz tridimensional* de temperaturas aéreas en varios puntos de un volumen tridimensional.

```vb
Dim airTemperatures(99, 99, 24) As Single
```

### <a name="more-than-three-dimensions"></a>Más de tres dimensiones

Aunque una matriz puede tener hasta 32 dimensiones, es poco habitual tener más de tres.

> [!NOTE]
> Al agregar dimensiones a una matriz, el almacenamiento total que necesita la matriz aumenta considerablemente, por lo que debe usar matrices multidimensionales con cuidado.

## <a name="using-different-dimensions"></a>Usar dimensiones diferentes

Supongamos que desea realizar un seguimiento de los importes de ventas de cada día del mes presente. Podría declarar una matriz unidimensional con 31 elementos, uno para cada día del mes, como se muestra en el ejemplo siguiente.

```vb
Dim salesAmounts(30) As Double
```

Ahora Supongamos que desea realizar un seguimiento de la misma información no solo para cada día de un mes, sino también para cada mes del año. Podría declarar una matriz bidimensional con 12 filas (para los meses) y 31 columnas (para los días), como se muestra en el ejemplo siguiente.

```vb
Dim salesAmounts(11, 30) As Double
```

Ahora Supongamos que decide que la matriz contiene información durante más de un año. Si desea realizar un seguimiento de los importes de ventas durante 5 años, puede declarar una matriz tridimensional con 5 capas, 12 filas y 31 columnas, como se muestra en el ejemplo siguiente.

```vb
Dim salesAmounts(4, 11, 30) As Double
```

Tenga en cuenta que, dado que cada índice varía de 0 a su máximo, cada dimensión de `salesAmounts` se declara como una menor que la longitud necesaria para esa dimensión. Tenga en cuenta también que el tamaño de la matriz aumenta con cada nueva dimensión. Los tres tamaños de los ejemplos anteriores son los elementos 31, 372 y 1.860, respectivamente.

> [!NOTE]
> Puede crear una matriz sin usar la `Dim` instrucción o la `New` cláusula. Por ejemplo, puede llamar al <xref:System.Array.CreateInstance%2A> método u otro componente puede pasar el código a una matriz creada de esta manera. Este tipo de matriz puede tener un límite inferior distinto de 0. Siempre puede probar el límite inferior de una dimensión mediante el <xref:System.Array.GetLowerBound%2A> método o la `LBound` función.

## <a name="see-also"></a>Vea también

- [Matrices](index.md)
- [Solución de problemas de matrices](troubleshooting-arrays.md)
