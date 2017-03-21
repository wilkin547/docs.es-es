---
title: Me, My, MyBase y MyClass en Visual Basic | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
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
dev_langs:
- VB
helpviewer_keywords:
- My object
- self-reference, Me keyword
- MyClass keyword, relationship to similar programming elements
- Me keyword, relationship to similar programming elements
- Me keyword, referring to the current instance of an object
- Me keyword
- self-reference
- current instance, Me keyword
- MyBase keyword, relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: 15
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 59dba8961712537367db9a60e8b8ba68bcb6a1ea
ms.lasthandoff: 03/13/2017

---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase y MyClass en Visual Basic
`Me`, `My`, `MyBase`, y `MyClass` en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tienen nombres similares, pero con distintos fines. Este tema describe cada una de estas entidades para distinguirlas.  
  
## <a name="me"></a>Me  
 El `Me` (palabra clave) proporciona una manera de hacer referencia a la instancia específica de una clase o estructura en la que se está ejecutando el código. `Me`se comporta como una variable de objeto o una variable de estructura que hace referencia a la instancia actual. Mediante `Me` es especialmente útil para pasar información sobre la instancia en ejecución de una clase o estructura a un procedimiento de otra clase, estructura o módulo.  
  
 Por ejemplo, suponga que tiene el siguiente procedimiento en un módulo.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Puede llamar a este procedimiento y pasar la instancia actual de la <xref:System.Windows.Forms.Form>clase como un argumento mediante la siguiente instrucción.</xref:System.Windows.Forms.Form>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 El `My` característica proporciona acceso fácil e intuitivo a un número de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] clases, habilitar la [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] usuario interactúe con el equipo, aplicación, configuración, recursos y así sucesivamente.  
  
## <a name="mybase"></a>MyBase  
 El `MyBase` (palabra clave) se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase. `MyBase`se utiliza normalmente para tener acceso a miembros de clase base que se reemplazan o se sombrean en una clase derivada. `MyBase.New`se utiliza para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.  
  
## <a name="myclass"></a>MyClass  
 El `MyClass` (palabra clave) se comporta como una variable de objeto que hace referencia a la instancia actual de una clase se implementó originalmente. `MyClass`es similar a `Me`, pero todas las llamadas de método en él se tratan como si fuera el método `NotOverridable`.  
  
## <a name="see-also"></a>Vea también  
 [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
