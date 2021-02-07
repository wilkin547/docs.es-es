---
description: 'Más información acerca de: ReadOnly (Visual Basic)'
title: ReadOnly
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: f510271531f6e6604f2b542d8331d1a1d7f64d58
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700915"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)

Especifica que una variable o una propiedad se puede leer pero no escribir.

## <a name="remarks"></a>Observaciones

## <a name="rules"></a>Reglas

- **Contexto de declaración.** Solo se puede usar `ReadOnly` en un nivel de módulo. Esto significa que el contexto de la declaración de un `ReadOnly` elemento debe ser una clase, una estructura o un módulo, y no puede ser un archivo de código fuente, un espacio de nombres o un procedimiento.

- **Modificadores combinados.** No se puede especificar `ReadOnly` junto con `Static` en la misma declaración.

- **Asignación de un valor.** El código que consume una `ReadOnly` propiedad no puede establecer su valor. Pero el código que tiene acceso al almacenamiento subyacente puede asignar o cambiar el valor en cualquier momento.

     Puede asignar un valor a una `ReadOnly` variable solo en su declaración o en el constructor de una clase o estructura en la que se define.

## <a name="when-to-use-a-readonly-variable"></a>Cuándo usar una variable de solo lectura

Hay situaciones en las que no se puede usar una [instrucción const](../statements/const-statement.md) para declarar y asignar un valor constante. Por ejemplo, `Const` es posible que la instrucción no acepte el tipo de datos que desea asignar o que no pueda calcular el valor en tiempo de compilación con una expresión constante. Es posible que ni siquiera conozca el valor en tiempo de compilación. En estos casos, puede usar una `ReadOnly` variable para contener un valor constante.

> [!IMPORTANT]
> Si el tipo de datos de la variable es un tipo de referencia, como una matriz o una instancia de clase, se pueden cambiar sus miembros aunque la propia variable sea `ReadOnly` . Esto se ilustra en el siguiente ejemplo:

```vb
ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}
Sub ChangeArrayElement()
    characterArray(1) = "M"c
End Sub
```

Cuando se inicializa, la matriz a la que señala `characterArray()` contiene "x", "y" y "z". Dado que la variable `characterArray` es `ReadOnly` , no se puede cambiar su valor una vez inicializado; es decir, no se puede asignar una nueva matriz a ella. Sin embargo, puede cambiar los valores de uno o varios de los miembros de la matriz. Después de una llamada al procedimiento `ChangeArrayElement` , la matriz a la que señala `characterArray()` contiene "x", "M" y "z".

Tenga en cuenta que esto es similar a declarar un parámetro de procedimiento como [ByVal](byval.md), lo que evita que el procedimiento cambie el argumento de llamada en sí, pero permite cambiar sus miembros.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se define una `ReadOnly` propiedad para la fecha en la que se contrató a un empleado. La clase almacena el valor de propiedad internamente como una `Private` variable y solo el código dentro de la clase puede cambiar ese valor. Sin embargo, la propiedad es `Public` , y cualquier código que pueda tener acceso a la clase puede leer la propiedad.

[!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]

El modificador `ReadOnly` se puede utilizar en los contextos siguientes:

- [Instrucción Dim](../statements/dim-statement.md)
- [Property Statement](../statements/property-statement.md)

## <a name="see-also"></a>Vea también

- [WriteOnly](writeonly.md)
- [Palabras clave](../keywords/index.md)
