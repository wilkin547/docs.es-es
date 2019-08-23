---
title: Acceso de miembro compartido mediante una instancia; la expresión calificadora no se evaluará
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 3174d463744303e8c90ed0b2e1a4d86ed08fbcfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947700"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Acceso de miembro compartido mediante una instancia; la expresión calificadora no se evaluará
Una variable de instancia de una clase o estructura se utiliza para tener `Shared` acceso a una variable, propiedad, procedimiento o evento definidos en esa clase o estructura. Esta advertencia también puede producirse si se usa una variable de instancia para tener acceso a un miembro compartido implícitamente de una clase o estructura, como una constante o una enumeración, o una clase o estructura anidada.  
  
 El propósito de compartir un miembro es crear una sola copia de ese miembro y hacer que esa copia única esté disponible para cada instancia de la clase o estructura en la que se declara. Es coherente con este propósito para tener acceso a `Shared` un miembro mediante el nombre de su clase o estructura, en lugar de una variable que contiene una instancia individual de esa clase o estructura.  
  
 El acceso a `Shared` un miembro a través de una variable de instancia puede hacer que el código sea más difícil de entender ocultando el `Shared`hecho de que el miembro es. Además, si dicho acceso forma parte de una expresión que realiza otras acciones, como un `Function` procedimiento que devuelve una instancia del miembro compartido, Visual Basic omite la expresión y otras acciones que, de otro modo, realizarían.  
  
 Para obtener más información y un ejemplo, vea [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 De forma predeterminada, este mensaje es una advertencia. Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **IDENTIFICADOR de error:** BC42025  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Use el nombre de la clase o estructura que define el `Shared` miembro para tener acceso a él, tal como se muestra en el ejemplo siguiente.  
  
```vb  
Public Class testClass  
    Public Shared Sub sayHello()  
        MsgBox("Hello")  
    End Sub  
End Class  
  
Module testModule  
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New testClass  
        tc.sayHello()  
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        testClass.sayHello()  
    End Sub  
End Module  
```  
  
> [!NOTE]
> Debe alertar sobre los efectos del ámbito cuando dos elementos de programación tienen el mismo nombre. En el ejemplo anterior, si declara una instancia `Dim testClass as testClass = Nothing`de mediante, el compilador trata una llamada a `testClass.sayHello()` como un acceso al método mediante el nombre de clase y no se produce ninguna advertencia.  
  
## <a name="see-also"></a>Vea también

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Ámbito en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
