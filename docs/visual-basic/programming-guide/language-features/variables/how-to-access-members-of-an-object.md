---
title: "Cómo: Obtener acceso a los miembros de un objeto (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 85fa4932b449bf7b9ecb3902fc17fd954ea8cfac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Cómo: Obtener acceso a los miembros de un objeto (Visual Basic)
Si tiene una variable de objeto que hace referencia a un objeto, a menudo desea trabajar con los miembros de ese objeto, como sus métodos, propiedades, campos y eventos. Por ejemplo, una vez haya creado un nuevo <xref:System.Windows.Forms.Form> objeto, conviene establecer su <xref:System.Windows.Forms.Control.Text%2A> propiedad o llamada a su <xref:System.Windows.Forms.Control.Focus%2A> método.  
  
## <a name="accessing-members"></a>Obtener acceso a miembros  
 Obtener acceso a los miembros de un objeto a través de la variable que hace referencia a él.  
  
#### <a name="to-access-members-of-an-object"></a>Para obtener acceso a miembros de un objeto  
  
-   Utilice el operador de acceso a miembros (`.`) entre el nombre de variable de objeto y el nombre de miembro.  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     Si el miembro es [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), no necesita una variable para tener acceso a él.  
  
## <a name="accessing-members-of-an-object-of-known-type"></a>Obtener acceso a miembros de un objeto de tipo conocido  
 Si conoce el tipo de un objeto en tiempo de compilación, puede usar *el enlace anticipado* para una variable que hace referencia a él.  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>Para obtener acceso a miembros de un objeto para el que se conoce el tipo en tiempo de compilación  
  
1.  Declare la variable de objeto para ser del tipo del objeto que se va a asignar a la variable.  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     Con `Option Strict On`, puede asignar solo <xref:System.Windows.Forms.Form> objetos (o los objetos de un tipo derivan de <xref:System.Windows.Forms.Form>) a `extraForm`. Si ha definido una clase o estructura con una ampliación `CType` conversión a <xref:System.Windows.Forms.Form>, también puede asignar esa clase o estructura a `extraForm`.  
  
2.  Utilice el operador de acceso a miembros (`.`) entre el nombre de variable de objeto y el nombre de miembro.  
  
    ```  
    extraForm.Show()  
    ```  
  
     Puede tener acceso a todos los métodos y propiedades específicas de la <xref:System.Windows.Forms.Form> (clase), independientemente del `Option Strict` configuración es.  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a>Obtener acceso a miembros de un objeto de tipo desconocido  
 Si no conoce el tipo de un objeto en tiempo de compilación, debe usar *enlace más tarde* para cualquier variable que hace referencia a él.  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Para obtener acceso a miembros de un objeto para el que no conoce el tipo en tiempo de compilación  
  
1.  Declare la variable de objeto de la [tipo de datos de objeto](../../../../visual-basic/language-reference/data-types/object-data-type.md). (Declarar una variable como `Object` es el mismo que declararla como como <xref:System.Object?displayProperty=nameWithType>.)  
  
    ```  
    Dim someControl As Object  
    ```  
  
     Con `Option Strict On`, puede tener acceso a solo los miembros que se definen en la <xref:System.Object> clase.  
  
2.  Utilice el operador de acceso a miembros (`.`) entre el nombre de variable de objeto y el nombre de miembro.  
  
    ```  
    someControl.GetType()  
    ```  
  
     Para poder tener acceso a los miembros de cualquier objeto que se asigna a la variable de objeto, debe establecer `Option Strict Off`. Al hacerlo, el compilador no puede garantizar que un miembro determinado se expone mediante el objeto que asigna a la variable. Si el objeto no expone un miembro al que intenta tener acceso, un <xref:System.MemberAccessException> se produce una excepción.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Object>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.MemberAccessException>  
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
