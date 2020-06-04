---
title: Uso de la varianza en delegados
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: 842392a1342f7d3689d4d1f2a2adb7470eeda05e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375789"
---
# <a name="using-variance-in-delegates-visual-basic"></a>Usar varianza en delegados (Visual Basic)

Al asignar un método a un delegado, la *covarianza* y la *contravarianza* proporcionan flexibilidad para hacer coincidir un tipo de delegado con una firma de método. La covarianza permite que un método tenga un tipo de valor devuelto más derivado que el definido en el delegado. La contravarianza permite un método que tiene tipos de parámetro menos derivados que los del tipo de delegado.

## <a name="example-1-covariance"></a>Ejemplo 1: covarianza

### <a name="description"></a>Description

En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen tipos de valor devuelto derivados del tipo de valor devuelto en la firma del delegado. El tipo de datos devuelto por `DogsHandler` es de tipo `Dogs`, que se deriva del tipo `Mammals` definido en el delegado.

### <a name="code"></a>Código

```vb
Class Mammals
End Class

Class Dogs
    Inherits Mammals
End Class
Class Test
    Public Delegate Function HandlerMethod() As Mammals
    Public Shared Function MammalsHandler() As Mammals
        Return Nothing
    End Function
    Public Shared Function DogsHandler() As Dogs
        Return Nothing
    End Function
    Sub Test()
        Dim handlerMammals As HandlerMethod = AddressOf MammalsHandler
        ' Covariance enables this assignment.
        Dim handlerDogs As HandlerMethod = AddressOf DogsHandler
    End Sub
End Class
```

## <a name="example-2-contravariance"></a>Ejemplo 2: contravarianza

### <a name="description"></a>Description

En este ejemplo se muestra cómo se pueden usar delegados con métodos que tienen parámetros que son tipos base del tipo de parámetro de la firma del delegado. Con la contravarianza, puede usar un controlador de eventos en lugar de controladores independientes. En el ejemplo siguiente se usan dos delegados:

- Un delegado <xref:System.Windows.Forms.KeyEventHandler> que define la firma del evento [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown). Su firma es:

   ```vb
   Public Delegate Sub KeyEventHandler(sender As Object, e As KeyEventArgs)
   ```

- Un delegado <xref:System.Windows.Forms.MouseEventHandler> que define la firma del evento [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown). Su firma es:

   ```vb
   Public Delegate Sub MouseEventHandler(sender As Object, e As MouseEventArgs)
   ```

En el ejemplo se define un controlador de eventos con un parámetro <xref:System.EventArgs>, que se usa para controlar los eventos `Button.KeyDown` y `Button.MouseClick`. Es posible hacer esto porque <xref:System.EventArgs> es un tipo base de <xref:System.Windows.Forms.KeyEventArgs> y <xref:System.Windows.Forms.MouseEventArgs>.

### <a name="code"></a>Código

```vb
' Event handler that accepts a parameter of the EventArgs type.
Private Sub MultiHandler(ByVal sender As Object,
                         ByVal e As System.EventArgs)
    Label1.Text = DateTime.Now
End Sub

Private Sub Form1_Load(ByVal sender As System.Object,
    ByVal e As System.EventArgs) Handles MyBase.Load

    ' You can use a method that has an EventArgs parameter,
    ' although the event expects the KeyEventArgs parameter.
    AddHandler Button1.KeyDown, AddressOf MultiHandler

    ' You can use the same method
    ' for the event that expects the MouseEventArgs parameter.
    AddHandler Button1.MouseClick, AddressOf MultiHandler
End Sub
```

## <a name="see-also"></a>Vea también

- [Varianza en delegados (Visual Basic)](variance-in-delegates.md)
- [Usar la varianza para los delegados genéricos Func y Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md)
