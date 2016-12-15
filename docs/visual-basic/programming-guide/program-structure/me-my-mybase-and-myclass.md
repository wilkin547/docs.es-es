---
title: "Me, My, MyBase y MyClass en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MyClass"
  - "vb.Me"
  - "MyBase"
  - "vb.MyBase"
  - "Me"
  - "vb.MyClass"
  - "vb.This"
  - "vb.My"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "instancia actual, Me (palabra clave)"
  - "Me (palabra clave)"
  - "Me (palabra clave), hacer referencia a la instancia actual de un objeto"
  - "Me (palabra clave), relación con elementos de programación similares"
  - "My (objeto)"
  - "MyBase (palabra clave), relación con elementos de programación similares"
  - "MyClass (palabra clave), relación con elementos de programación similares"
  - "autorreferencia"
  - "autorreferencia, Me (palabra clave)"
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Me, My, MyBase y MyClass en Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`Me`, `My`, `MyBase` y `MyClass` en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] tienen nombres similares pero finalidades diferentes.  En esta tema se describe cada una de estas entidades para distinguirlas.  
  
## Me  
 La palabra clave `Me` siempre hace referencia a la instancia específica de una clase o estructura donde se está ejecutando el código.  `Me` se comporta como una variable de objeto o de estructura que hace referencia a la instancia actual.  El uso de la palabra clave `Me` es especialmente útil para transferir información acerca de la instancia de una clase o estructura que se está ejecutando actualmente a un procedimiento de otro módulo, estructura o clase.  
  
 Por ejemplo, suponga que dispone del siguiente procedimiento en un módulo.  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 Puede llamar a este procedimiento y pasar como argumento la instancia actual de la clase <xref:System.Windows.Forms.Form> mediante la instrucción siguiente.  
  
```  
ChangeFormColor(Me)  
```  
  
## My  
 La característica `My` proporciona acceso fácil e intuitivo a una serie de clases de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], lo que permite que el usuario de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] interactúe con el equipo, la aplicación, la configuración, los recursos, etc.  
  
## MyBase  
 La palabra clave `MyBase` se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase.  `MyBase` suele usarse para obtener acceso a los miembros de la clase base que se reemplazan o se sombrean en una clase derivada.  `MyBase.New` se utiliza para llamar explícitamente a un constructor de una clase base desde un constructor de una clase derivada.  
  
## MyClass  
 La palabra clave `MyClass` se comporta como una variable de objeto que hace referencia a la instancia actual de una clase tal y como se implementó originalmente.  `MyClass` es similar a `Me`, pero todas las llamadas de método realizadas a través de ella se tratan como si el método fuese `NotOverridable`.  
  
## Vea también  
 [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)