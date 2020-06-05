---
title: Tipos de datos compuestos
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
ms.openlocfilehash: 3e8df5ccfeca4bc0a19237ba6d59e9d0747080ea
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84394303"
---
# <a name="composite-data-types-visual-basic"></a>Tipos de datos compuestos (Visual Basic)
Además de los tipos de datos elementales Visual Basic proporciona, también puede ensamblar elementos de tipos diferentes para crear *tipos de datos compuestos* como estructuras, matrices y clases. Puede crear tipos de datos compuestos a partir de tipos elementales y de otros tipos compuestos. Por ejemplo, puede definir una matriz de elementos de estructura o una estructura con miembros de matriz.  
  
## <a name="data-types"></a>Tipo de datos  
 Un tipo compuesto es diferente del tipo de datos de cualquiera de sus componentes. Por ejemplo, una matriz de `Integer` elementos no es del `Integer` tipo de datos.  
  
 Normalmente, un tipo de datos de matriz se representa mediante el tipo de elemento, paréntesis y comas según sea necesario. Por ejemplo, una matriz unidimensional de `String` elementos se representa como `String()` y una matriz bidimensional de `Boolean` elementos se representa como `Boolean(,)` .  
  
## <a name="structure-types"></a>Tipos de estructura  
 No hay ningún tipo de datos único que incluya todas las estructuras. En su lugar, cada definición de una estructura representa un tipo de datos único, incluso si dos estructuras definen elementos idénticos en el mismo orden. Sin embargo, si crea dos o más instancias de la misma estructura, Visual Basic considera que son del mismo tipo de datos.  
  
## <a name="tuples"></a>Tuplas

Una tupla es una estructura ligera que contiene dos o más campos cuyos tipos están predefinidos. Las tuplas se admiten a partir de Visual Basic 2017. Las tuplas se suelen usar para devolver varios valores de una sola llamada al método sin tener que pasar argumentos por referencia o empaquetar los campos devueltos en una estructura o clase más pesada. Vea el tema sobre [tuplas](tuples.md) para obtener más información sobre las tuplas.

## <a name="array-types"></a>Tipos de matriz  
 No hay ningún tipo de datos único que comprenda todas las matrices. El tipo de datos de una instancia determinada de una matriz viene determinado por lo siguiente:  
  
- El hecho de ser una matriz  
  
- Rango (número de dimensiones) de la matriz.  
  
- El tipo de elemento de la matriz.  
  
 En concreto, la longitud de una dimensión determinada no forma parte del tipo de datos de la instancia. Esto se ilustra en el siguiente ejemplo.  
  
```vb  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 En el ejemplo anterior, las variables `arrayA` de matriz y `arrayB` se consideran del mismo tipo de datos, `Byte()` aunque se inicializan en longitudes diferentes. Las variables `arrayB` y `arrayC` no son del mismo tipo porque sus tipos de elemento son diferentes. Las variables `arrayC` y `arrayD` no son del mismo tipo porque sus rangos son diferentes. Variables `arrayD` y `arrayE` tienen el mismo tipo ( `Short(,)` ) porque sus rangos y tipos de elemento son los mismos, aunque `arrayD` aún no se ha inicializado.  
  
 Para obtener más información sobre las matrices, vea [matrices](../arrays/index.md).  
  
## <a name="class-types"></a>Tipos de clase  
 No hay ningún tipo de datos único que incluya todas las clases. Aunque una clase puede heredar de otra clase, cada una es un tipo de datos independiente. Varias instancias de la misma clase tienen el mismo tipo de datos. Si asigna una variable de instancia de clase a otra, y no solo tienen el mismo tipo de datos, apuntan a la misma instancia de clase en la memoria.  
  
 Para obtener más información sobre las clases, vea [objetos y clases](../objects-and-classes/index.md).  
  
## <a name="see-also"></a>Consulte también

- [Tipos de datos](index.md)
- [Tipos de datos básicos](elementary-data-types.md)
- [Tipos genéricos en Visual Basic](generic-types.md)
- [Tipos de valor y tipos de referencia](value-types-and-reference-types.md)
- [Conversiones de tipos en Visual Basic](type-conversions.md)
- [Estructuras](structures.md)
- [Solución de problemas de los tipos de datos](troubleshooting-data-types.md)
- [Procedimiento Inclusión de más de un valor en una variable](how-to-hold-more-than-one-value-in-a-variable.md)
