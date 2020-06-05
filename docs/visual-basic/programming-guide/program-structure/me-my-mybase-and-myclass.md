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
ms.openlocfilehash: b4470e5c178c0f66dc33956ea0131d4eabc51d46
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397498"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a>Me, My, MyBase y MyClass en Visual Basic
`Me`, `My` , `MyBase` y `MyClass` en Visual Basic tienen nombres similares, pero con fines diferentes. En este tema se describe cada una de estas entidades con el fin de distinguirlas.  
  
## <a name="me"></a>Yo  
 La `Me` palabra clave proporciona una manera de hacer referencia a la instancia específica de una clase o estructura en la que el código se está ejecutando actualmente. `Me`se comporta como una variable de objeto o una variable de estructura que hace referencia a la instancia actual. El uso de `Me` es especialmente útil para pasar información sobre la instancia que se está ejecutando actualmente de una clase o estructura a un procedimiento de otra clase, estructura o módulo.  
  
 Por ejemplo, supongamos que tiene el siguiente procedimiento en un módulo.  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Puede llamar a este procedimiento y pasar la instancia actual de la <xref:System.Windows.Forms.Form> clase como argumento mediante la siguiente instrucción.  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a>My  
 La `My` característica proporciona acceso sencillo e intuitivo a una serie de clases de .NET Framework, lo que permite al usuario Visual Basic interactuar con el equipo, la aplicación, la configuración, los recursos, etc.  
  
## <a name="mybase"></a>MyBase  
 La `MyBase` palabra clave se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase. `MyBase`se utiliza normalmente para tener acceso a los miembros de clase base que se invalidan o se sombrean en una clase derivada. `MyBase.New`se usa para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.  
  
## <a name="myclass"></a>MyClass  
 La `MyClass` palabra clave se comporta como una variable de objeto que hace referencia a la instancia actual de una clase como se implementó originalmente. `MyClass`es similar a `Me` , pero todas las llamadas a métodos en él se tratan como si el método fuera `NotOverridable` .  
  
## <a name="see-also"></a>Consulte también

- [Fundamentos de la herencia](../language-features/objects-and-classes/inheritance-basics.md)
