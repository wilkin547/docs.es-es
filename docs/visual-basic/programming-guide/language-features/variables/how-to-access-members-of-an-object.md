---
title: 'Cómo: Obtener acceso a los miembros de un objeto'
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: d44b538e8413eb1412e937375e9bca77600a29b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348665"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Cómo: Obtener acceso a los miembros de un objeto (Visual Basic)

Si tiene una variable de objeto que hace referencia a un objeto, a menudo desea trabajar con los miembros de ese objeto, como sus métodos, propiedades, campos y eventos. Por ejemplo, una vez que haya creado un nuevo objeto <xref:System.Windows.Forms.Form>, es posible que desee establecer su <xref:System.Windows.Forms.Control.Text%2A> propiedad o llamar a su método <xref:System.Windows.Forms.Control.Focus%2A>.

## <a name="accessing-members"></a>Obtener acceso a miembros

Puede tener acceso a los miembros de un objeto a través de la variable que hace referencia a él.

#### <a name="to-access-members-of-an-object"></a>Para tener acceso a los miembros de un objeto

- Use el operador de acceso a miembros (`.`) entre el nombre de la variable de objeto y el nombre del miembro.

    ```vb
    currentText = newForm.Text
    ```

    Si el miembro es [compartido](../../../../visual-basic/language-reference/modifiers/shared.md), no necesita una variable para tener acceso a él.

## <a name="accessing-members-of-an-object-of-known-type"></a>Obtener acceso a miembros de un objeto de tipo conocido

Si conoce el tipo de un objeto en tiempo de compilación, puede usar el *enlace temprano* para una variable que haga referencia a él.

#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>Para obtener acceso a los miembros de un objeto para el que conoce el tipo en tiempo de compilación

1. Declare la variable de objeto para que sea del tipo del objeto que desea asignar a la variable.

    ```vb
    Dim extraForm As System.Windows.Forms.Form
    ```

    Con `Option Strict On`, solo puede asignar objetos <xref:System.Windows.Forms.Form> (u objetos de un tipo derivado de <xref:System.Windows.Forms.Form>) a `extraForm`. Si ha definido una clase o estructura con una conversión de `CType` de ampliación en <xref:System.Windows.Forms.Form>, también puede asignar esa clase o estructura a `extraForm`.

2. Use el operador de acceso a miembros (`.`) entre el nombre de la variable de objeto y el nombre del miembro.

    ```vb
    extraForm.Show()
    ```

    Puede tener acceso a todos los métodos y propiedades específicos de la clase <xref:System.Windows.Forms.Form>, con independencia de cuál sea la configuración de `Option Strict`.

## <a name="accessing-members-of-an-object-of-unknown-type"></a>Obtener acceso a miembros de un objeto de tipo desconocido

Si no conoce el tipo de un objeto en tiempo de compilación, debe utilizar el enlace en tiempo de *ejecución* para cualquier variable que haga referencia a él.

#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Para tener acceso a los miembros de un objeto para el que no conoce el tipo en tiempo de compilación

1. Declare la variable de objeto para que sea del [tipo de datos Object](../../../../visual-basic/language-reference/data-types/object-data-type.md). (Declarar una variable como `Object` es igual que declarar como <xref:System.Object?displayProperty=nameWithType>).

    ```vb
    Dim someControl As Object
    ```

    Con `Option Strict On`, solo puede tener acceso a los miembros que se definen en la clase <xref:System.Object>.

2. Use el operador de acceso a miembros (`.`) entre el nombre de la variable de objeto y el nombre del miembro.

    ```vb
    someControl.GetType()
    ```

    Para poder tener acceso a los miembros de cualquier objeto que asigne a la variable de objeto, debe establecer `Option Strict Off`. Al hacerlo, el compilador no puede garantizar que un miembro determinado esté expuesto por el objeto que se asigna a la variable. Si el objeto no expone un miembro al que se intenta obtener acceso, se produce una excepción <xref:System.MemberAccessException>.

## <a name="see-also"></a>Vea también

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
