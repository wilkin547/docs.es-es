---
title: "Definir valores predeterminados con los métodos ShouldSerialize y Reset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d082b0e3db1e1c115d28446cf515cf6acf60a7d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>Definir valores predeterminados con los métodos ShouldSerialize y Reset
`ShouldSerialize`y `Reset` son métodos opcionales que se pueden proporcionar para una propiedad, si la propiedad no es un valor predeterminado simple. Si la propiedad tiene un valor predeterminado simple, debe aplicar el <xref:System.ComponentModel.DefaultValueAttribute> y proporcionar el valor predeterminado para el constructor de clase de atributo en su lugar. Cualquiera de estos mecanismos habilita las siguientes características en el diseñador:  
  
-   La propiedad proporciona una indicación visual en el Explorador de propiedades si se ha modificado el valor predeterminado.  
  
-   El usuario puede haga doble clic en la propiedad y elija **restablecer** para restaurar la propiedad a su valor predeterminado.  
  
-   El diseñador genera código más eficaz.  
  
    > [!NOTE]
    >  Ya sea aplicar el <xref:System.ComponentModel.DefaultValueAttribute> o proporcionar `Reset` *PropertyName* y `ShouldSerialize` *PropertyName* métodos. No utilice ambos.  
  
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
>  Si una propiedad no tiene un `Reset` método, no se marca con un <xref:System.ComponentModel.DefaultValueAttribute>y no tiene un valor predeterminado proporcionado en su declaración, la `Reset` opción para esa propiedad está deshabilitada en el menú contextual de la **propiedades** ventana del Diseñador de Windows Forms en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
 Los diseñadores como [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] usar la `ShouldSerialize` *PropertyName* se cambia el método para comprobar si una propiedad ha cambiado respecto de su valor predeterminado y escribir código en el solo si forma una propiedad, permitiendo así de más eficaz generación de código. Por ejemplo:  
  
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
  
 En este caso, incluso cuando el valor de la variable privada obtiene acceso a la `MyFont` propiedad es `null`, el Explorador de propiedades no muestra `null`; en su lugar, muestra la <xref:System.Windows.Forms.Control.Font%2A> propiedad del elemento primario, si no lo es `null`, o el valor predeterminado <xref:System.Windows.Forms.Control.Font%2A> valor definido en <xref:System.Windows.Forms.Control>. Por lo tanto, el valor predeterminado de `MyFont` no se puede establecer simplemente y un <xref:System.ComponentModel.DefaultValueAttribute> no se puede aplicar a esta propiedad. En su lugar, el `ShouldSerialize` y `Reset` deben implementar los métodos para la `MyFont` propiedad.  
  
## <a name="see-also"></a>Vea también  
 [Propiedades de los controles de Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [Definir una propiedad](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 [Eventos de cambio de propiedades](../../../../docs/framework/winforms/controls/property-changed-events.md)
