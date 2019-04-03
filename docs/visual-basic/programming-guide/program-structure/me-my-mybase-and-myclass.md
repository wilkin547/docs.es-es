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
ms.openlocfilehash: a8df6e48fd5bce9bb28d8aef7e031f36741ad0ad
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813397"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase y MyClass en Visual Basic
`Me`, `My`, `MyBase`, y `MyClass` en Visual Basic tienen nombres similares, pero con distintos fines. Este tema describe cada una de estas entidades para distinguirlos.  
  
## <a name="me"></a>Me  
 El `Me` palabra clave proporciona una manera de hacer referencia a la instancia específica de una clase o estructura en la que se está ejecutando el código. `Me` se comporta como una variable de objeto o una variable de estructura que hace referencia a la instancia actual. Uso de `Me` es especialmente útil para pasar información sobre la instancia en ejecución de una clase o estructura a un procedimiento de otra clase, estructura o módulo.  
  
 Por ejemplo, suponga que tiene el siguiente procedimiento en un módulo.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Puede llamar a este procedimiento y pasar la instancia actual de la <xref:System.Windows.Forms.Form> clase como un argumento mediante la instrucción siguiente.  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 El `My` característica proporciona acceso fácil e intuitivo a un número de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] clases, que permite al usuario de Visual Basic interactuar con el equipo, aplicación, configuración, recursos y así sucesivamente.  
  
## <a name="mybase"></a>MyBase  
 El `MyBase` palabra clave se comporta como una variable de objeto que hace referencia a la clase de la instancia actual de una clase base. `MyBase` se utiliza normalmente para tener acceso a los miembros de clase base que se reemplazan o sombrean en una clase derivada. `MyBase.New` se usa para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.  
  
## <a name="myclass"></a>MyClass  
 El `MyClass` palabra clave se comporta como una variable de objeto que hace referencia a la instancia actual de una clase como se implementaron originalmente. `MyClass` es similar a `Me`, pero todas las llamadas de método en él se tratan como si fuera el método `NotOverridable`.  
  
## <a name="see-also"></a>Vea también

- [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
