---
title: Me, My, MyBase y MyClass
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
ms.openlocfilehash: a21dfeb12e8d99f5f8b8afede084846711c299ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401434"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase y MyClass en Visual Basic
`Me`, `My` `MyBase`, `MyClass` , y en Visual Basic tienen nombres similares, pero diferentes propósitos. En este tema se describe cada una de estas entidades para distinguirlas.  
  
## <a name="me"></a>Yo  
 La `Me` palabra clave proporciona una manera de hacer referencia a la instancia específica de una clase o estructura en la que el código se está ejecutando actualmente. `Me`se comporta como una variable de objeto o una variable de estructura que hace referencia a la instancia actual. El `Me` uso es especialmente útil para pasar información sobre la instancia que se está ejecutando actualmente de una clase o estructura a un procedimiento de otra clase, estructura o módulo.  
  
 Por ejemplo, supongamos que tiene el siguiente procedimiento en un módulo.  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Puede llamar a este procedimiento y <xref:System.Windows.Forms.Form> pasar la instancia actual de la clase como argumento mediante la instrucción siguiente.  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 La `My` característica proporciona un acceso fácil e intuitivo a varias clases de .NET Framework, lo que permite al usuario de Visual Basic interactuar con el equipo, la aplicación, la configuración, los recursos, etc.  
  
## <a name="mybase"></a>MyBase  
 La `MyBase` palabra clave se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase. `MyBase`se utiliza comúnmente para tener acceso a los miembros de la clase base que se reemplazan o sombrean en una clase derivada. `MyBase.New`se utiliza para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.  
  
## <a name="myclass"></a>MyClass  
 La `MyClass` palabra clave se comporta como una variable de objeto que hace referencia a la instancia actual de una clase como implementada originalmente. `MyClass`es similar `Me`a , pero todas las llamadas `NotOverridable`al método en él se tratan como si el método fuera .  
  
## <a name="see-also"></a>Consulte también

- [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
