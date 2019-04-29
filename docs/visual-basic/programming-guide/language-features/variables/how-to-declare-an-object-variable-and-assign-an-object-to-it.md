---
title: Procedimiento Declarar una Variable de objeto y asignarle un objeto en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: fb6411efc190dce335422369a8d2bbff564b9523
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938221"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>Procedimiento Declarar una Variable de objeto y asignarle un objeto en Visual Basic
Declare una variable de la [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) especificando `As Object` en un [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md). Asignar un objeto a este tipo de variable colocando el objeto después del signo igual (`=`) en una cláusula de instrucción o la inicialización de la asignación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara un `Object` variable y asigna la instancia actual a él.  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 Puede combinar la declaración y asignación, inicialice la variable como parte de su declaración. El ejemplo siguiente es equivalente al ejemplo anterior.  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Una referencia al espacio de nombres <xref:System>.  
  
- Una clase, estructura o módulo en el que se va a colocar el `Dim` instrucción.  
  
- Un procedimiento en el que se va a colocar la instrucción de asignación.  
  
## <a name="see-also"></a>Vea también

- [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
