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
ms.openlocfilehash: f1f5a668c5d4f52ef7dd9f60a31c04f2173165f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090620"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>Definir valores predeterminados con los métodos ShouldSerialize y Reset
`ShouldSerialize` y `Reset` son métodos opcionales que puede proporcionar para una propiedad, si la propiedad no es un valor predeterminado simple. Si la propiedad tiene un valor predeterminado simple, debe aplicar el <xref:System.ComponentModel.DefaultValueAttribute> y proporcionar el valor predeterminado para el constructor de clase de atributo en su lugar. Cualquiera de estos mecanismos habilita las siguientes características en el diseñador:  
  
-   La propiedad proporciona una indicación visual en el Explorador de propiedades si se ha modificado desde su valor predeterminado.  
  
-   El usuario puede hacer doble clic en la propiedad y elija **restablecer** para restaurar la propiedad a su valor predeterminado.  
  
-   El diseñador genera código más eficaz.  
  
    > [!NOTE]
    >  Se aplica ya sea el <xref:System.ComponentModel.DefaultValueAttribute> o proporcionar `Reset` *PropertyName* y `ShouldSerialize` *PropertyName* métodos. No use ambos.  
  
 El `Reset` *PropertyName* método establece una propiedad en su valor predeterminado, tal como se muestra en el siguiente fragmento de código.  
  
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
>  Si no tiene una propiedad de un `Reset` método, no está marcado con un <xref:System.ComponentModel.DefaultValueAttribute>y no tiene un valor predeterminado en su declaración, el `Reset` opción para esa propiedad está deshabilitada en el menú contextual de la **propiedades** ventana del Diseñador de Windows Forms en Visual Studio.  
  
 Los diseñadores como Visual Studio usan el `ShouldSerialize` *PropertyName* se cambia el método para comprobar si una propiedad ha cambiado desde su valor predeterminado y escribir código en el solo si forma una propiedad, lo que permite para un código más eficaz generación. Por ejemplo:  
  
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
  
 Sigue un ejemplo de código completo.  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
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
using System.Windows.Forms;  
using System.Drawing;  
  
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
  
 En este caso, incluso cuando el valor de la variable privada obtiene acceso a la `MyFont` propiedad es `null`, no se muestra el Explorador de propiedades `null`; en su lugar, muestra el <xref:System.Windows.Forms.Control.Font%2A> propiedad del elemento primario, si no es `null`, o el valor predeterminado <xref:System.Windows.Forms.Control.Font%2A> valor definido en <xref:System.Windows.Forms.Control>. Por lo tanto, el valor predeterminado de `MyFont` no se puede establecer simplemente y un <xref:System.ComponentModel.DefaultValueAttribute> no se puede aplicar a esta propiedad. En su lugar, el `ShouldSerialize` y `Reset` se deben implementar los métodos para la `MyFont` propiedad.  
  
## <a name="see-also"></a>Vea también

- [Propiedades de los controles de formularios Windows Forms](properties-in-windows-forms-controls.md)
- [Definir una propiedad](defining-a-property-in-windows-forms-controls.md)
- [Eventos de cambio de propiedades](property-changed-events.md)
