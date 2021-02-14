---
description: 'Más información acerca de cómo: obtener acceso a los miembros de un objeto (Visual Basic)'
title: Procedimiento para obtener acceso a los miembros de un objeto
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: b4aed213bbe520b7b7027acc146d0973f7273fd1
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100435530"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Cómo: Obtener acceso a los miembros de un objeto (Visual Basic)

Si tiene una variable de objeto que hace referencia a un objeto, a menudo desea trabajar con los miembros de ese objeto, como sus métodos, propiedades, campos y eventos. Por ejemplo, una vez que haya creado un nuevo <xref:System.Windows.Forms.Form> objeto, es posible que desee establecer su <xref:System.Windows.Forms.Control.Text%2A> propiedad o llamar a su <xref:System.Windows.Forms.Control.Focus%2A> método.

## <a name="accessing-members"></a>Obtener acceso a miembros

Puede tener acceso a los miembros de un objeto a través de la variable que hace referencia a él.

#### <a name="to-access-members-of-an-object"></a>Para tener acceso a los miembros de un objeto

- Use el operador de acceso a miembros ( `.` ) entre el nombre de la variable de objeto y el nombre del miembro.

    ```vb
    currentText = newForm.Text
    ```

    Si el miembro es [compartido](../../../language-reference/modifiers/shared.md), no necesita una variable para tener acceso a él.

## <a name="accessing-members-of-an-object-of-known-type"></a>Obtener acceso a miembros de un objeto de tipo conocido

Si conoce el tipo de un objeto en tiempo de compilación, puede usar el *enlace temprano* para una variable que haga referencia a él.

#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>Para obtener acceso a los miembros de un objeto para el que conoce el tipo en tiempo de compilación

1. Declare la variable de objeto para que sea del tipo del objeto que desea asignar a la variable.

    ```vb
    Dim extraForm As System.Windows.Forms.Form
    ```

    Con `Option Strict On` , solo puede asignar <xref:System.Windows.Forms.Form> objetos (u objetos de un tipo derivado de <xref:System.Windows.Forms.Form> ) a `extraForm` . Si ha definido una clase o estructura con una conversión de ampliación `CType` a <xref:System.Windows.Forms.Form> , también puede asignar esa clase o estructura a `extraForm` .

2. Use el operador de acceso a miembros ( `.` ) entre el nombre de la variable de objeto y el nombre del miembro.

    ```vb
    extraForm.Show()
    ```

    Puede tener acceso a todos los métodos y propiedades específicos de la <xref:System.Windows.Forms.Form> clase, con independencia de cuál `Option Strict` sea la configuración.

## <a name="accessing-members-of-an-object-of-unknown-type"></a>Obtener acceso a miembros de un objeto de tipo desconocido

Si no conoce el tipo de un objeto en tiempo de compilación, debe utilizar el enlace en tiempo de *ejecución* para cualquier variable que haga referencia a él.

#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Para tener acceso a los miembros de un objeto para el que no conoce el tipo en tiempo de compilación

1. Declare la variable de objeto para que sea del [tipo de datos Object](../../../language-reference/data-types/object-data-type.md). (Declarar una variable como `Object` es igual que la declaración como <xref:System.Object?displayProperty=nameWithType> ).

    ```vb
    Dim someControl As Object
    ```

    Con `Option Strict On` , solo puede tener acceso a los miembros que se definen en la <xref:System.Object> clase.

2. Use el operador de acceso a miembros ( `.` ) entre el nombre de la variable de objeto y el nombre del miembro.

    ```vb
    someControl.GetType()
    ```

    Para poder tener acceso a los miembros de cualquier objeto que asigne a la variable de objeto, debe establecer `Option Strict Off` . Al hacerlo, el compilador no puede garantizar que un miembro determinado esté expuesto por el objeto que se asigna a la variable. Si el objeto no expone un miembro al que se intenta tener acceso, <xref:System.MemberAccessException> se produce una excepción.

## <a name="see-also"></a>Consulte también

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [Variables de objeto](object-variables.md)
- [Declaración de variables de objeto](object-variable-declaration.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Option Strict (instrucción)](../../../language-reference/statements/option-strict-statement.md)
