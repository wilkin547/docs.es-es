---
title: La expresión llama de forma recursiva a la propiedad contenedora '<propertyname>'
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: 42177f22e632e4a05b1f0b4d934f3e56ab9ff0f2
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698568"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a>La expresión llama de forma recursiva a la propiedad contenedora ' \<propertyname > '
Una instrucción en el procedimiento `Set` de una definición de propiedad almacena un valor en el nombre de la propiedad.  
  
 El enfoque recomendado para contener el valor de una propiedad es definir una variable `Private` en el contenedor de la propiedad y utilizarla en los procedimientos `Get` y `Set`. A continuación, el procedimiento `Set` debe almacenar el valor entrante en esta variable `Private`.  
  
 El procedimiento `Get` se comporta como un procedimiento `Function`, por lo que puede asignar un valor al nombre de la propiedad y devolver el control al encontrar la instrucción @no__t 2. Sin embargo, el enfoque recomendado consiste en incluir la variable `Private` como valor en una [instrucción return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 El procedimiento `Set` se comporta como un procedimiento `Sub`, que no devuelve un valor. Por lo tanto, el nombre del procedimiento o de la propiedad no tiene ningún significado especial dentro de un procedimiento `Set` y no se puede almacenar un valor en él.  
  
 En el ejemplo siguiente se muestra el enfoque que puede producir este error, seguido del enfoque recomendado.  
  
```vb  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 De forma predeterminada, este mensaje es una advertencia. Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **IDENTIFICADOR de error:** BC42026  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Vuelva a escribir la definición de la propiedad para usar el enfoque recomendado, tal como se muestra en el ejemplo anterior.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos de propiedades](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)
- [Set (instrucción)](../../../visual-basic/language-reference/statements/set-statement.md)
