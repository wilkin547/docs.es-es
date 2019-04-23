---
title: Procedimiento Obtener acceso a miembros de un objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: de00e428cc3d9d7a5688e853b0ff4295fec5b3e9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322763"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Procedimiento Obtener acceso a miembros de un objeto (Visual Basic)
Cuando haya una variable de objeto que hace referencia a un objeto, a menudo desea trabajar con los miembros de ese objeto, como sus métodos, propiedades, campos y eventos. Por ejemplo, una vez haya creado un nuevo <xref:System.Windows.Forms.Form> objeto que desea establecer su <xref:System.Windows.Forms.Control.Text%2A> propiedad o llamada a su <xref:System.Windows.Forms.Control.Focus%2A> método.  
  
## <a name="accessing-members"></a>Acceso a miembros  
 Tener acceso a los miembros de un objeto a través de la variable que hace referencia a él.  
  
#### <a name="to-access-members-of-an-object"></a>Para obtener acceso a miembros de un objeto  
  
-   Utilice el operador de acceso a miembros (`.`) entre el nombre de variable de objeto y el nombre del miembro.  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     Si el miembro es [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), no es necesario una variable para acceder a él.  
  
## <a name="accessing-members-of-an-object-of-known-type"></a>Acceso a miembros de un objeto de tipo conocido  
 Si conoce el tipo de un objeto en tiempo de compilación, puede usar *enlace anticipado* para una variable que hace referencia a él.  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>Para obtener acceso a miembros de un objeto para el que se conoce el tipo en tiempo de compilación  
  
1. Declare la variable de objeto para ser del tipo del objeto que se va a asignar a la variable.  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     Con `Option Strict On`, puede asignar solo <xref:System.Windows.Forms.Form> objetos (o los objetos de un tipo derivan de <xref:System.Windows.Forms.Form>) a `extraForm`. Si ha definido una clase o estructura con una ampliación `CType` conversión a <xref:System.Windows.Forms.Form>, también puede asignar esa clase o estructura a `extraForm`.  
  
2. Utilice el operador de acceso a miembros (`.`) entre el nombre de variable de objeto y el nombre del miembro.  
  
    ```  
    extraForm.Show()  
    ```  
  
     Puede tener acceso a todos los métodos y propiedades específicas de la <xref:System.Windows.Forms.Form> (clase), independientemente de lo que el `Option Strict` es la configuración.  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a>Acceso a miembros de un objeto de tipo desconocido  
 Si no conoce el tipo de un objeto en tiempo de compilación, debe usar *enlace más tarde* para cualquier variable que hace referencia a él.  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Para obtener acceso a miembros de un objeto para el que se desconoce el tipo en tiempo de compilación  
  
1. Declare la variable de objeto de la [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md). (Declarar una variable como `Object` es el mismo que su declaración como <xref:System.Object?displayProperty=nameWithType>.)  
  
    ```  
    Dim someControl As Object  
    ```  
  
     Con `Option Strict On`, puede tener acceso a solo los miembros que se definen en el <xref:System.Object> clase.  
  
2. Utilice el operador de acceso a miembros (`.`) entre el nombre de variable de objeto y el nombre del miembro.  
  
    ```  
    someControl.GetType()  
    ```  
  
     Para poder tener acceso a los miembros de cualquier objeto que se asigne a la variable de objeto, debe establecer `Option Strict Off`. Al hacerlo, el compilador no puede garantizar que un miembro determinado se expone mediante el objeto que se asigna a la variable. Si el objeto no expone un miembro que intenta tener acceso, un <xref:System.MemberAccessException> se produce una excepción.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
