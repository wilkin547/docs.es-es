---
title: Acceso de miembro compartido mediante una instancia; la expresión calificadora no se evaluará
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 035882b60c90d9a6141ad0d34b4c40682e0c32a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588988"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Acceso de miembro compartido mediante una instancia; la expresión calificadora no se evaluará
Se utiliza una variable de instancia de una clase o estructura para tener acceso a un `Shared` variable, propiedad, procedimiento o evento definido en esa clase o estructura. Esta advertencia también puede producirse si una variable de instancia se utiliza para tener acceso a un miembro implícitamente compartido de una clase o estructura, como una constante o enumeración, o una clase anidada o una estructura.  
  
 El propósito de compartir a un miembro es crear una sola copia de ese miembro y que esa sola copia esté disponible para todas las instancias de la clase o estructura en la que se declara. Es coherente con este fin para tener acceso a un `Shared` miembro mediante el nombre de su clase o estructura, y no a través de una variable que contiene una instancia individual de esa clase o estructura.  
  
 Obtener acceso a un `Shared` miembro a través de una variable de instancia puede hacer más difícil de entender ocultando el hecho de que el miembro es el código `Shared`. Además, si el acceso forma parte de una expresión que lleva a cabo otras acciones, como un `Function` procedimiento que devuelve una instancia del miembro compartido, Visual Basic omite la expresión y todas las demás acciones que realizaría en caso contrario.  
  
 Para obtener más información y un ejemplo, vea [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC42025  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Utilice el nombre de la clase o estructura que define el `Shared` miembro que se va a obtener acceso a él, tal como se muestra en el ejemplo siguiente.  
  
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
>  Aparecer la alerta para los efectos de ámbito cuando dos elementos de programación tienen el mismo nombre. En el ejemplo anterior, si se declara una instancia mediante el uso de `Dim testClass as testClass = Nothing`, el compilador trata una llamada a `testClass.sayHello()` tal y como se produce el acceso del método por el nombre de clase y ninguna advertencia.  
  
## <a name="see-also"></a>Vea también  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [Ámbito en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
