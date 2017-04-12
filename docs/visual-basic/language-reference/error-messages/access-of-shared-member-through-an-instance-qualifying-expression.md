---
title: "Acceso de miembro compartido mediante una instancia; la expresión calificadora no se evaluará | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42025
- BC42025
dev_langs:
- VB
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 39be3c95d5acc20afe3a33be9d4db48c09f99a9c
ms.lasthandoff: 03/13/2017

---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Acceso de miembro compartido mediante una instancia; la expresión calificadora no se evaluará
Se utiliza una variable de instancia de una clase o estructura para tener acceso a un `Shared` variable, propiedad, procedimiento o evento definido en esa clase o estructura. Esta advertencia también puede producirse si se utiliza una variable de instancia para tener acceso a un miembro implícitamente compartido de una clase o estructura, como una constante o enumeración, o una clase anidada o estructura.  
  
 El propósito de compartir a un miembro es crear una sola copia de ese miembro y que esa sola copia esté disponible para todas las instancias de la clase o estructura en la que se declara. Es coherente con este propósito, para tener acceso a un `Shared` miembro mediante el nombre de su clase o estructura, en lugar de una variable que contiene una instancia individual de esa clase o estructura.  
  
 Obtener acceso a un `Shared` miembro a través de una variable de instancia puede hacer su código más difícil de entender ocultando el hecho de que el miembro es `Shared`. Además, si el acceso forma parte de una expresión que realiza otras acciones, como un `Function` procedimiento que devuelve una instancia del miembro compartido, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] omite la expresión y otras acciones que realizaría en caso contrario.  
  
 Para obtener más información y un ejemplo, vea [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información acerca de cómo ocultar las advertencias o tratar las advertencias como errores, vea [configurar advertencias en Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC42025  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Utilice el nombre de la clase o estructura que define la `Shared` miembro para tener acceso a él, como se muestra en el ejemplo siguiente.  
  
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
>  Esté alerta para los efectos de ámbito cuando dos elementos de programación tienen el mismo nombre. En el ejemplo anterior, si se declara una instancia mediante `Dim testClass as testClass = Nothing`, el compilador trata una llamada a `testClass.sayHello()` tal como se produce el acceso del método por el nombre de clase y ninguna advertencia.  
  
## <a name="see-also"></a>Vea también  
 [Compartido](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Ámbito en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
