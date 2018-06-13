---
title: La expresión llama recursivamente la propiedad contenedora &#39; &lt;propertyname&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: f14e2645772b22a8f6ff2385dcd316a42d1d5cf0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588848"
---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a>La expresión llama recursivamente la propiedad contenedora &#39; &lt;propertyname&gt;&#39;
Una instrucción en el `Set` procedimiento con una definición de propiedad almacena un valor en el nombre de la propiedad.  
  
 El enfoque recomendado para conservar el valor de una propiedad consiste en definir un `Private` variable al contenedor de propiedades y utilizar tanto en el `Get` y `Set` procedimientos. El `Set` procedimiento, a continuación, debe almacenar el valor de entrada en este `Private` variable.  
  
 El `Get` procedimiento se comporta como un `Function` procedimiento, por lo que puede asignar un valor al nombre de propiedad y devolver el control cuando se encuentra el `End Get` instrucción. Sin embargo, es el enfoque recomendado, debe incluir el `Private` variable como el valor de un [instrucción Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 El `Set` procedimiento se comporta como un `Sub` procedimiento, que no devuelve un valor. Por lo tanto, el nombre de procedimiento o una propiedad no tiene ningún significado especial dentro de un `Set` procedimiento y no se puede almacenar un valor en él.  
  
 En el ejemplo siguiente se muestra el enfoque que puede producir este error, seguido por el enfoque recomendado.  
  
```  
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
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC42026  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Vuelva a escribir la definición de propiedad para utilizar el enfoque recomendado como se muestra en el ejemplo anterior.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos de propiedades](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Set (instrucción)](../../../visual-basic/language-reference/statements/set-statement.md)
