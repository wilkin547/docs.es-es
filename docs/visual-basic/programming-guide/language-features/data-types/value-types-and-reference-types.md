---
description: 'Más información sobre: tipos de valor y tipos de referencia'
title: Tipos de valor y tipos de referencia
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: 22cce68260955545e810f6fefe645b5ad6a37ca5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462144"
---
# <a name="value-types-and-reference-types"></a>Tipos de valor y tipos de referencia

Hay dos tipos de tipos en Visual Basic: tipos de referencia y tipos de valor. Las variables de tipos de referencia almacenan referencias en sus datos (objetos), mientras que las variables de tipos de valor contienen directamente los datos. Con los tipos de referencia, dos variables pueden hacer referencia al mismo objeto y, por lo tanto, las operaciones en una variable pueden afectar al objeto al que hace referencia la otra variable. Con los tipos de valor, cada variable tiene su propia copia de los datos y no es posible que las operaciones en una variable afecten a la otra (excepto en el caso del [modificador ByRef en parámetros](../../../language-reference/modifiers/byref.md)).
  
## <a name="value-types"></a>Tipos de valor  

 Un tipo de datos es un *tipo de valor* si contiene los datos dentro de su propia asignación de memoria. Entre los tipos de valor se incluyen los siguientes:  
  
- Todos los tipos de datos numéricos  
  
- `Boolean`, `Char` y `Date`  
  
- Todas las estructuras, incluso si sus miembros son tipos de referencia  
  
- Enumeraciones, ya que su tipo subyacente siempre es `SByte` , `Short` , `Integer` , `Long` , `Byte` , `UShort` , `UInteger` o. `ULong`  
  
 Cada estructura es un tipo de valor, incluso si contiene miembros de tipo de referencia. Por esta razón, los tipos de valor como `Char` y `Integer` se implementan mediante .NET Framework estructuras.  
  
 Puede declarar un tipo de valor mediante la palabra clave Reserved, por ejemplo, `Decimal` . También puede usar la `New` palabra clave para inicializar un tipo de valor. Esto es especialmente útil si el tipo tiene un constructor que toma parámetros. Un ejemplo de esto es el <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, que genera un nuevo `Decimal` valor a partir de los elementos proporcionados.  
  
## <a name="reference-types"></a>Tipos de referencia  

 Un *tipo de referencia* almacena una referencia a sus datos. Entre los tipos de referencia se incluyen los siguientes:  
  
- `String`  
  
- Todas las matrices, incluso si sus elementos son tipos de valor  
  
- Tipos de clase, como <xref:System.Windows.Forms.Form>  
  
- Delegados  
  
 Una clase es un *tipo de referencia*. Tenga en cuenta que cada matriz es un tipo de referencia, incluso si sus miembros son tipos de valor.  
  
 Puesto que cada tipo de referencia representa una clase de .NET Framework subyacente, debe usar la palabra clave [New Operator](../../../language-reference/operators/new-operator.md) al inicializarla. La siguiente instrucción Inicializa una matriz.  
  
```vb  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>Elementos que no son tipos  

 Los elementos de programación siguientes no se califican como tipos, ya que no se puede especificar ninguno de ellos como un tipo de datos para un elemento declarado:  
  
- Espacios de nombres  
  
- Módulos  
  
- Eventos  
  
- Propiedades y procedimientos  
  
- Variables, constantes y campos  
  
## <a name="working-with-the-object-data-type"></a>Trabajar con el tipo de datos Object  

 Puede asignar un tipo de referencia o un tipo de valor a una variable del `Object` tipo de datos. Una `Object` variable siempre contiene una referencia a los datos, nunca los propios datos. Sin embargo, si asigna un tipo de valor a una `Object` variable, se comporta como si tuviera sus propios datos. Para obtener más información, vea [Object Data Type](../../../language-reference/data-types/object-data-type.md).  
  
 Puede averiguar si una `Object` variable actúa como un tipo de referencia o un tipo de valor pasándola al <xref:Microsoft.VisualBasic.Information.IsReference%2A> método en la <xref:Microsoft.VisualBasic.Information> clase del <xref:Microsoft.VisualBasic?displayProperty=nameWithType> espacio de nombres. <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> Devuelve `True` si el contenido de la `Object` variable representa un tipo de referencia.  
  
## <a name="see-also"></a>Consulte también

- [Tipos de valor que aceptan valores NULL](nullable-value-types.md)
- [Conversiones de tipos en Visual Basic](type-conversions.md)
- [Structure (Instrucción)](../../../language-reference/statements/structure-statement.md)
- [Uso eficiente de los tipos de datos](efficient-use-of-data-types.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Tipo de datos](index.md)
