---
title: Procedimiento Declare una variable de objeto y asígnele un objeto en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 71949d50b01d7f252a988e86ca259261086d3b3b
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630876"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>Procedimiento Declare una variable de objeto y asígnele un objeto en Visual Basic

Declare una variable del [tipo de datos Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) especificando `As Object` en una [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md). Para asignar un objeto a esta variable, coloque el objeto después del signo igual (`=`) en una instrucción de asignación o una cláusula de inicialización.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se declara `Object` una variable y se le asigna la instancia actual.

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

Puede combinar la declaración y la asignación inicializando la variable como parte de su declaración. El ejemplo siguiente es equivalente al ejemplo anterior.

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compiling-the-code"></a>Compilar el código

Para este ejemplo se necesita:

- Una referencia al espacio de nombres <xref:System>.

- Clase, estructura o módulo en el que se va a colocar `Dim` la instrucción.

- Procedimiento en el que se va a colocar la instrucción de asignación.

## <a name="see-also"></a>Vea también

- [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
