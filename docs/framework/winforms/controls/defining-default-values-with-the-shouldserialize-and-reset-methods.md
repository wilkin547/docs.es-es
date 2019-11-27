---
title: Definir valores predeterminados con los métodos ShouldSerialize y Reset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
ms.openlocfilehash: 11181bacdb919693ffc82c48c061357463a6343b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336764"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>Definir valores predeterminados con los métodos ShouldSerialize y Reset
`ShouldSerialize` y `Reset` son métodos opcionales que puede proporcionar para una propiedad si la propiedad no tiene un valor predeterminado simple. Si la propiedad tiene un valor predeterminado simple, debe aplicar el <xref:System.ComponentModel.DefaultValueAttribute> y proporcionar el valor predeterminado al constructor de clase de atributo en su lugar. Cualquiera de estos mecanismos habilita las siguientes características en el diseñador:

- La propiedad proporciona una indicación visual en el explorador de propiedades si se ha modificado a partir de su valor predeterminado.

- El usuario puede hacer clic con el botón derecho en la propiedad y elegir **restablecer** para restaurar el valor predeterminado de la propiedad.

- El diseñador genera código más eficaz.

    > [!NOTE]
    > Aplique el <xref:System.ComponentModel.DefaultValueAttribute> o proporcione los métodos `Reset`*PropertyName* y `ShouldSerialize`*PropertyName* . No use ambos.

 El método `Reset`*PropertyName* establece una propiedad en su valor predeterminado, tal y como se muestra en el siguiente fragmento de código.

```vb
Public Sub ResetMyFont()
   MyFont = Nothing
End Sub
```

```csharp
public void ResetMyFont() {
   MyFont = null;
}
```

> [!NOTE]
> Si una propiedad no tiene un método `Reset`, no está marcado con un <xref:System.ComponentModel.DefaultValueAttribute>y no tiene un valor predeterminado proporcionado en su declaración, la opción `Reset` de esa propiedad está deshabilitada en el menú contextual de la ventana **propiedades** del diseñador de Windows Forms en Visual Studio.

 Los diseñadores como Visual Studio usan el método `ShouldSerialize`*PropertyName* para comprobar si una propiedad ha cambiado respecto a su valor predeterminado y escribir código en el formulario solo si se cambia una propiedad, lo que permite una generación de código más eficaz. Por ejemplo:

```vb
'Returns true if the font has changed; otherwise, returns false.
' The designer writes code to the form only if true is returned.
Public Function ShouldSerializeMyFont() As Boolean
   Return Not (thefont Is Nothing)
End Function
```

```csharp
// Returns true if the font has changed; otherwise, returns false.
// The designer writes code to the form only if true is returned.
public bool ShouldSerializeMyFont() {
   return thefont != null;
}
```

 A continuación se muestra un ejemplo de código completo.

```vb
Option Explicit
Option Strict

Imports System.Drawing
Imports System.Windows.Forms

Public Class MyControl
   Inherits Control

   ' Declare an instance of the Font class
   ' and set its default value to Nothing.
   Private thefont As Font = Nothing

   ' The MyFont property.
   Public Property MyFont() As Font
      ' Note that the Font property never
      ' returns null.
      Get
         If Not (thefont Is Nothing) Then
            Return thefont
         End If
         If Not (Parent Is Nothing) Then
            Return Parent.Font
         End If
         Return Control.DefaultFont
      End Get
      Set
         thefont = value
      End Set
   End Property

   Public Function ShouldSerializeMyFont() As Boolean
      Return Not (thefont Is Nothing)
   End Function

   Public Sub ResetMyFont()
      MyFont = Nothing
   End Sub
End Class
```

```csharp
using System;
using System.Drawing;
using System.Windows.Forms;

public class MyControl : Control {
   // Declare an instance of the Font class
   // and set its default value to null.
   private Font thefont = null;

   // The MyFont property.
   public Font MyFont {
      // Note that the MyFont property never
      // returns null.
      get {
         if (thefont != null) return thefont;
         if (Parent != null) return Parent.Font;
         return Control.DefaultFont;
      }
      set {
         thefont = value;
      }
   }

   public bool ShouldSerializeMyFont() {
      return thefont != null;
   }

   public void ResetMyFont() {
      MyFont = null;
   }
}
```

 En este caso, incluso cuando el valor de la variable privada a la que tiene acceso la propiedad `MyFont` es `null`, el explorador de propiedades no muestra `null`; en su lugar, muestra la propiedad <xref:System.Windows.Forms.Control.Font%2A> del elemento primario, si no se `null`, o el valor predeterminado de <xref:System.Windows.Forms.Control.Font%2A> definido en <xref:System.Windows.Forms.Control>. Por lo tanto, el valor predeterminado de `MyFont` no se puede establecer simplemente y no se puede aplicar un <xref:System.ComponentModel.DefaultValueAttribute> a esta propiedad. En su lugar, se deben implementar los métodos `ShouldSerialize` y `Reset` para la propiedad `MyFont`.

## <a name="see-also"></a>Vea también

- [Propiedades de los controles de Windows Forms](properties-in-windows-forms-controls.md)
- [Definir una propiedad](defining-a-property-in-windows-forms-controls.md)
- [Eventos de cambio de propiedades](property-changed-events.md)
