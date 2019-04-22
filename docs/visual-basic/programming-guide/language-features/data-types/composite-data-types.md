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
ms.openlocfilehash: ea719b60a6bcd40494666d4923fad296a8ddae70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833820"
---
# <a name="composite-data-types-visual-basic"></a>Tipos de datos compuestos (Visual Basic)
Además de los tipos de datos básicos que proporciona Visual Basic, también puede ensamblar los elementos de distintos tipos para crear *tipos de datos compuestos* como clases, matrices y estructuras. Puede crear tipos de datos compuestos de tipos elementales y de otros tipos compuestos. Por ejemplo, puede definir una matriz de elementos de estructura o una estructura con miembros de la matriz.  
  
## <a name="data-types"></a>Tipos de datos  
 Un tipo compuesto es diferente del tipo de datos de cualquiera de sus componentes. Por ejemplo, una matriz de `Integer` elementos no es de la `Integer` tipo de datos.  
  
 Un tipo de datos de matriz normalmente se representa mediante el tipo de elemento, paréntesis y comas según sea necesario. Por ejemplo, una matriz unidimensional de `String` elementos se representa como `String()`y una matriz bidimensional de `Boolean` elementos se representa como `Boolean(,)`.  
  
## <a name="structure-types"></a>Tipos de estructura  
 No hay ningún tipo de datos que incluye todas las estructuras. En su lugar, cada definición de una estructura representa un tipo de datos único, incluso si dos estructuras de definan elementos idénticos en el mismo orden. Sin embargo, si crea dos o más instancias de la misma estructura, Visual Basic considera que son del mismo tipo de datos.  
  
## <a name="tuples"></a>Tuplas

Una tupla es una estructura ligera que contiene dos o más campos cuyos tipos predefinidos. Las tuplas se admiten a partir de Visual Basic 2017. Las tuplas se usan normalmente para devolver varios valores de una única llamada al método sin tener que pasar argumentos por referencia o empaquetar los campos devueltos en una clase o estructura con más ligeras y pesadas. Consulte la [tuplas](tuples.md) tema para obtener más información sobre las tuplas.

## <a name="array-types"></a>Tipos de matriz  
 No hay ningún tipo de datos que incluya todas las matrices. El tipo de datos de una instancia determinada de una matriz se determina por el texto siguiente:  
  
-   El hecho de ser una matriz  
  
-   El rango (número de dimensiones) de la matriz  
  
-   El tipo de elemento de la matriz  
  
 En concreto, la longitud de una dimensión determinada no es parte de la instancia tipo de datos. Esto se ilustra en el siguiente ejemplo:  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 En el ejemplo anterior, las variables de matriz `arrayA` y `arrayB` se consideran del mismo tipo de datos: `Byte()` , aunque se hayan inicializado con distintas longitudes. Las variables `arrayB` y `arrayC` no son del mismo tipo, porque sus tipos de elemento son diferentes. Las variables `arrayC` y `arrayD` no son del mismo tipo porque sus rangos son diferentes. Las variables `arrayD` y `arrayE` tienen el mismo tipo — `Short(,)` , porque sus rangos y tipos de elemento son los mismos, aunque `arrayD` aún no está inicializado.  
  
 Para obtener más información sobre matrices, vea [matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="class-types"></a>Tipos de clase  
 No hay ningún tipo de datos que incluye todas las clases. Aunque una clase puede heredar de otra clase, cada uno de ellos es un tipo de datos independiente. Varias instancias de la misma clase son del mismo tipo de datos. Si asigna una variable de instancia de clase a otra, no sólo tienen los mismos datos de tipo, que señalan a la misma instancia de clase en la memoria.  
  
 Para obtener más información sobre las clases, vea [objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Cómo: Contener más de un valor en una variable](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
