---
title: Me, My, MyBase y MyClass en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bebf404cd65d1b3a2c4059d3a7c986f0157dfe2d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase y MyClass en Visual Basic
`Me`, `My`, `MyBase`, y `MyClass` en [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] tienen nombres similares, pero distintos fines. Este tema describe cada una de estas entidades para distinguirlas.  
  
## <a name="me"></a>Me  
 El `Me` (palabra clave) proporciona una manera de hacer referencia a la instancia específica de una clase o estructura en la que se esté ejecutando el código. `Me`se comporta como una variable de objeto o una variable de estructura que hace referencia a la instancia actual. Usar `Me` es especialmente útil para pasar información sobre la instancia actualmente en ejecución de una clase o estructura a un procedimiento en otra clase, estructura o módulo.  
  
 Por ejemplo, suponga que tiene el siguiente procedimiento en un módulo.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Puede llamar a este procedimiento y pasar la instancia actual de la <xref:System.Windows.Forms.Form> clase como un argumento mediante la siguiente instrucción.  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 El `My` característica proporciona acceso fácil e intuitivo a un número de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] clases, habilitar la [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] al usuario interactuar con el equipo, aplicación, configuración, recursos y así sucesivamente.  
  
## <a name="mybase"></a>MyBase  
 El `MyBase` palabra clave se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase. `MyBase`se suele utilizar para tener acceso a miembros de clase base que se reemplazan o se sombrean en una clase derivada. `MyBase.New`se utiliza para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.  
  
## <a name="myclass"></a>MyClass  
 El `MyClass` palabra clave se comporta como una variable de objeto que hace referencia a la instancia actual de una clase como se implementaron originalmente. `MyClass`es similar a `Me`, pero todas las llamadas de método en él se tratan como si fuera el método `NotOverridable`.  
  
## <a name="see-also"></a>Vea también  
 [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
