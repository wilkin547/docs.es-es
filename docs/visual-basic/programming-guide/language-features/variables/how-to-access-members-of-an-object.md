---
title: Procedimiento Obtener acceso a los miembros de un objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: 882046b829ade2da7c10b3db4c0d6c9ca9f3d579
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630831"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Procedimiento Obtener acceso a los miembros de un objeto (Visual Basic)

Si tiene una variable de objeto que hace referencia a un objeto, a menudo desea trabajar con los miembros de ese objeto, como sus métodos, propiedades, campos y eventos. Por ejemplo, una vez que haya creado un <xref:System.Windows.Forms.Form> nuevo objeto, es posible que desee establecer <xref:System.Windows.Forms.Control.Text%2A> su propiedad o llamar <xref:System.Windows.Forms.Control.Focus%2A> a su método.

## <a name="accessing-members"></a>Obtener acceso a miembros

Puede tener acceso a los miembros de un objeto a través de la variable que hace referencia a él.

#### <a name="to-access-members-of-an-object"></a>Para tener acceso a los miembros de un objeto

- Use el operador de acceso a miembros`.`() entre el nombre de la variable de objeto y el nombre del miembro.

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

    Con `Option Strict On`, solo <xref:System.Windows.Forms.Form> puede asignar objetos (u objetos de un tipo derivado de <xref:System.Windows.Forms.Form>) a `extraForm`. Si ha definido una clase o estructura con una `CType` conversión de ampliación a <xref:System.Windows.Forms.Form>, también puede asignar esa clase o estructura a `extraForm`.

2. Use el operador de acceso a miembros`.`() entre el nombre de la variable de objeto y el nombre del miembro.

    ```vb
    extraForm.Show()
    ```

    Puede tener acceso a todos los métodos y propiedades específicos de la <xref:System.Windows.Forms.Form> clase, con independencia de cuál `Option Strict` sea la configuración.

## <a name="accessing-members-of-an-object-of-unknown-type"></a>Obtener acceso a miembros de un objeto de tipo desconocido

Si no conoce el tipo de un objeto en tiempo de compilación, debe utilizar el enlace en tiempo de *ejecución* para cualquier variable que haga referencia a él.

#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Para tener acceso a los miembros de un objeto para el que no conoce el tipo en tiempo de compilación

1. Declare la variable de objeto para que sea del [tipo de datos Object](../../../../visual-basic/language-reference/data-types/object-data-type.md). (Declarar una variable como `Object` es igual que la declaración como <xref:System.Object?displayProperty=nameWithType>).

    ```vb
    Dim someControl As Object
    ```

    Con `Option Strict On`, solo puede tener acceso a los miembros que se definen en <xref:System.Object> la clase.

2. Use el operador de acceso a miembros`.`() entre el nombre de la variable de objeto y el nombre del miembro.

    ```vb
    someControl.GetType()
    ```

    Para poder tener acceso a los miembros de cualquier objeto que asigne a la variable de objeto, debe establecer `Option Strict Off`. Al hacerlo, el compilador no puede garantizar que un miembro determinado esté expuesto por el objeto que se asigna a la variable. Si el objeto no expone un miembro al que se intenta tener acceso, <xref:System.MemberAccessException> se produce una excepción.

## <a name="see-also"></a>Vea también

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
