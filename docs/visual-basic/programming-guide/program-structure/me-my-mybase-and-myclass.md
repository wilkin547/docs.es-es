---
title: Me, My, MyBase y MyClass en Visual Basic
ms.date: 07/20/2015
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
ms.openlocfilehash: f3db5f8f6688e68992f683ac1b1465078aa41231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650532"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase y MyClass en Visual Basic
`Me`, `My`, `MyBase`, y `MyClass` en Visual Basic tienen nombres similares, pero distintos fines. Este tema describe cada una de estas entidades para distinguirlas.  
  
## <a name="me"></a>Me  
 El `Me` (palabra clave) proporciona una manera de hacer referencia a la instancia específica de una clase o estructura en la que se esté ejecutando el código. `Me` se comporta como una variable de objeto o una variable de estructura que hace referencia a la instancia actual. Usar `Me` es especialmente útil para pasar información sobre la instancia actualmente en ejecución de una clase o estructura a un procedimiento en otra clase, estructura o módulo.  
  
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
 El `My` característica proporciona acceso fácil e intuitivo a un número de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] clases, permitir que el usuario de Visual Basic interactuar con el equipo, aplicación, configuración, recursos y así sucesivamente.  
  
## <a name="mybase"></a>MyBase  
 El `MyBase` palabra clave se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase. `MyBase` se suele utilizar para tener acceso a miembros de clase base que se reemplazan o se sombrean en una clase derivada. `MyBase.New` se utiliza para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.  
  
## <a name="myclass"></a>MyClass  
 El `MyClass` palabra clave se comporta como una variable de objeto que hace referencia a la instancia actual de una clase como se implementaron originalmente. `MyClass` es similar a `Me`, pero todas las llamadas de método en él se tratan como si fuera el método `NotOverridable`.  
  
## <a name="see-also"></a>Vea también  
 [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
