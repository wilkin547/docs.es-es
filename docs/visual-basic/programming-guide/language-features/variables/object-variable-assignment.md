---
title: Asignación de variables de objeto
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
ms.openlocfilehash: 9ae1a307e8c886166d516140b7f100a411cedcfa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410379"
---
# <a name="object-variable-assignment-visual-basic"></a>Asignación de variables de objeto (Visual Basic)

Use una instrucción de asignación normal para asignar un objeto a una variable de objeto. Puede asignar una expresión de objeto o la palabra clave [Nothing](../../../language-reference/nothing.md) , como se muestra en el ejemplo siguiente.

```vb
Dim thisObject As Object
' The following statement assigns an object reference.
thisObject = Form1
' The following statement discontinues association with any object.
thisObject = Nothing
```

`Nothing`significa que no hay ningún objeto asignado actualmente a la variable.

## <a name="initialization"></a>Inicialización

Cuando el código comienza a ejecutarse, las variables de objeto se inicializan en `Nothing` . Las declaraciones que incluyen la inicialización se reinicializan en los valores que se especifican cuando se ejecutan las instrucciones de declaración.

Puede incluir la inicialización en la declaración mediante la palabra clave [New](../../../language-reference/operators/new-operator.md) . Las siguientes instrucciones de declaración declaran variables de objeto `testUri` y `ver` y asignan objetos específicos a ellas. Cada usa uno de los constructores sobrecargados de la clase adecuada para inicializar el objeto.

```vb
Dim testUri As New System.Uri("https://www.microsoft.com")
Dim ver As New System.Version(6, 1, 0)
```

## <a name="disassociation"></a>Desasociación

Al establecer una variable de objeto en, se `Nothing` interrumpe la Asociación de la variable con cualquier objeto específico. Esto evita que cambie accidentalmente el objeto cambiando la variable. También permite probar si la variable de objeto apunta a un objeto válido, como se muestra en el ejemplo siguiente.

```vb
If otherObject IsNot Nothing Then
    ' otherObject refers to a valid object, so your code can use it.
End If
```

Si el objeto al que hace referencia la variable está en otra aplicación, esta prueba no puede determinar si la aplicación ha terminado o simplemente invalidado el objeto.

Una variable de objeto con un valor de `Nothing` también se denomina *referencia nula*.

## <a name="current-instance"></a>Instancia actual

La *instancia actual* de un objeto es aquella en la que se está ejecutando el código. Dado que todo el código se ejecuta dentro de un procedimiento, la instancia actual es aquella en la que se invocó el procedimiento.

La `Me` palabra clave actúa como una variable de objeto que hace referencia a la instancia actual. Si un procedimiento no está [compartido](../../../language-reference/modifiers/shared.md), puede usar la `Me` palabra clave para obtener un puntero a la instancia actual. Los procedimientos compartidos no se pueden asociar a una instancia específica de una clase.

`Me`El uso de es especialmente útil para pasar la instancia actual a un procedimiento de otro módulo. Por ejemplo, supongamos que tiene varios documentos XML y desea agregar texto estándar a todos ellos. En el ejemplo siguiente se define un procedimiento para hacerlo.

```vb
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)
    XmlDoc.CreateTextNode("This text goes into every XML document.")
End Sub
```

Cada objeto de documento XML podría llamar al procedimiento y pasar su instancia actual como argumento. El ejemplo siguiente demuestra este patrón.

```vb
addStandardText(Me)
```

## <a name="see-also"></a>Consulte también

- [Variables de objeto](object-variables.md)
- [Declaración de variables de objeto](object-variable-declaration.md)
- [Valores de las variables de objeto](object-variable-values.md)
- [Cómo: Declarar una variable de objeto y asignarle un objeto en Visual Basic](how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [Procedimiento para crear una variable de objeto que no haga referencia a ninguna instancia](how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [Me, My, MyBase y MyClass](../../program-structure/me-my-mybase-and-myclass.md)
