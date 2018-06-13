---
title: Tipos de datos compuestos (Visual Basic)
ms.date: 04/25/2017
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
ms.openlocfilehash: 73867a5881db7c94d258e8716c4ff4c5b1119e71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650444"
---
# <a name="composite-data-types-visual-basic"></a>Tipos de datos compuestos (Visual Basic)
Además de los tipos de datos básicos que proporciona Visual Basic, también puede juntar elementos de distintos tipos para crear *tipos de datos compuestos* como estructuras, matrices y clases. Puede crear tipos de datos compuestos de tipos elementales y de otros tipos compuestos. Por ejemplo, puede definir una matriz de elementos de estructura o una estructura con miembros de la matriz.  
  
## <a name="data-types"></a>Tipos de datos  
 Un tipo compuesto es diferente del tipo de datos de cualquiera de sus componentes. Por ejemplo, una matriz de `Integer` elementos no es de la `Integer` tipo de datos.  
  
 Un tipo de datos de matriz normalmente se representa mediante el tipo de elemento, paréntesis y comas según sea necesario. Por ejemplo, una matriz unidimensional de `String` elementos se representa como `String()`y una matriz bidimensional de `Boolean` elementos se representa como `Boolean(,)`.  
  
## <a name="structure-types"></a>Tipos de estructura  
 No hay ningún tipo de datos único que incluya todas las estructuras. En su lugar, cada definición de una estructura representa un tipo de datos único, aunque dos estructuras definan elementos idénticos en el mismo orden. Sin embargo, si crea dos o más instancias de la misma estructura, Visual Basic considera que son del mismo tipo de datos.  
  
## <a name="tuples"></a>Tuplas

Una tupla es una estructura ligera que contiene dos o más campos cuyos tipos predefinidos. Tuplas se admiten a partir de Visual Basic de 2017. Tuplas se utilizan normalmente para devolver varios valores de una única llamada al método sin tener que pasar argumentos por referencia o empaquetado de los campos devueltos en una clase o estructura con más exhaustiva. Consulte la [tuplas](tuples.md) tema para obtener más información sobre tuplas.

## <a name="array-types"></a>Tipos de matriz  
 No hay ningún tipo de datos que incluya todas las matrices. El tipo de datos de una instancia determinada de una matriz se determina por el texto siguiente:  
  
-   El hecho de ser una matriz  
  
-   El rango (número de dimensiones) de la matriz  
  
-   El tipo de elemento de la matriz  
  
 En concreto, la longitud de una dimensión determinada no forma parte de la instancia tipo de datos. Esto se ilustra en el siguiente ejemplo:  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 En el ejemplo anterior, las variables de matriz `arrayA` y `arrayB` se consideran del mismo tipo de datos: `Byte()` , aunque se hayan inicializado con distintas longitudes. Las variables `arrayB` y `arrayC` no son del mismo tipo porque sus tipos de elemento son diferentes. Las variables `arrayC` y `arrayD` no son del mismo tipo porque sus rangos son diferentes. Las variables `arrayD` y `arrayE` tienen el mismo tipo: `Short(,)` , porque sus rangos y tipos de elemento son los mismos, aunque `arrayD` aún no se inicializó.  
  
 Para obtener más información sobre matrices, vea [matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="class-types"></a>Tipos de clase  
 No hay ningún tipo de datos único que incluya todas las clases. Aunque una clase puede heredar de otra clase, cada uno de ellos es un tipo de datos independiente. Varias instancias de la misma clase son del mismo tipo de datos. Si asigna una variable de instancia de clase a otro, no solo ¿tienen los mismos datos de tipo, que señalan a la misma instancia de clase en la memoria.  
  
 Para obtener más información sobre las clases, vea [objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Tipos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Contener más de un valor en una variable](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
