---
description: 'Más información sobre: Cómo: declarar una variable de objeto y asignarle un objeto en Visual Basic'
title: Procedimiento para declarar una variable de objeto y asignarle un objeto
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: f79cda4507a3dbf2a6946dee7d909b6d1b10802d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481953"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>Cómo: Declarar una variable de objeto y asignarle un objeto en Visual Basic

Declare una variable del [tipo de datos Object](../../../language-reference/data-types/object-data-type.md) especificando `As Object` en una [instrucción Dim](../../../language-reference/statements/dim-statement.md). Para asignar un objeto a esta variable, coloque el objeto después del signo igual ( `=` ) en una instrucción de asignación o una cláusula de inicialización.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se declara una `Object` variable y se le asigna la instancia actual.

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

Puede combinar la declaración y la asignación inicializando la variable como parte de su declaración. El ejemplo siguiente es equivalente al ejemplo anterior.

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compile-the-code"></a>Compilar el código

Para este ejemplo se necesita:

- Una referencia al espacio de nombres <xref:System>.

- Clase, estructura o módulo en el que se va a colocar la `Dim` instrucción.

- Procedimiento en el que se va a colocar la instrucción de asignación.

## <a name="see-also"></a>Consulte también

- [Declaración de variable](variable-declaration.md)
- [Variables de objeto](object-variables.md)
- [Declaración de variables de objeto](object-variable-declaration.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Instrucción Dim](../../../language-reference/statements/dim-statement.md)
- [Inferencia de tipo de variable local](local-type-inference.md)
- [Option Strict (instrucción)](../../../language-reference/statements/option-strict-statement.md)
