---
title: Acceso de miembro compartido mediante una instancia; la expresión calificadora no se evaluará
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 8e6ddab16c59d7ce95d96b377e3f372f6ebe5278
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843570"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Acceso de miembro compartido mediante una instancia; la expresión calificadora no se evaluará
Una variable de instancia de una clase o estructura se usa para tener acceso a un `Shared` variable, propiedad, procedimiento o evento definido en esa clase o estructura. Esta advertencia puede producirse también si se usa una variable de instancia para tener acceso a un miembro implícitamente compartido de una clase o estructura, como una constante o enumeración, o una clase anidada o estructura.  
  
 El propósito de compartir a un miembro es crear una sola copia de dicho miembro y que dicha copia solo esté disponible para todas las instancias de la clase o estructura en la que se ha declarado. Es coherente con este fin para tener acceso a un `Shared` miembro mediante el nombre de su clase o estructura, en lugar de una variable que contiene una instancia individual de esa clase o estructura.  
  
 Obtener acceso a un `Shared` miembro a través de una variable de instancia puede hacer que su código más difícil de entender ocultando el hecho de que el miembro es `Shared`. Además, si el acceso forma parte de una expresión que lleva a cabo otras acciones, como un `Function` procedimiento que devuelve una instancia del miembro compartido, Visual Basic omite la expresión y todas las demás acciones realizaría en caso contrario.  
  
 Para obtener más información y un ejemplo, vea [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 De forma predeterminada, este mensaje es una advertencia. Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC42025  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Use el nombre de la clase o estructura que define el `Shared` miembro para acceder a él, como se muestra en el ejemplo siguiente.  
  
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
>  Esté alerta para los efectos de ámbito cuando dos elementos de programación tienen el mismo nombre. En el ejemplo anterior, si declara una instancia mediante el uso de `Dim testClass as testClass = Nothing`, el compilador trata una llamada a `testClass.sayHello()` tal como se produce el acceso del método mediante el nombre de clase y ninguna advertencia.  
  
## <a name="see-also"></a>Vea también

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Ámbito en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
