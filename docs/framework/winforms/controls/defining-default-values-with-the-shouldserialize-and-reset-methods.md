---
title: "Definir valores predeterminados con los m&#233;todos ShouldSerialize y Reset | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles personalizados [Windows Forms], métodos de propiedades"
  - "Reset (método)"
  - "ShouldPersist (método)"
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Definir valores predeterminados con los m&#233;todos ShouldSerialize y Reset
`ShouldSerialize` y `Reset` son métodos opcionales que se pueden proporcionar para una propiedad que no posea un valor predeterminado simple.  Si la propiedad posee un valor predeterminado simple, se debe aplicar el atributo <xref:System.ComponentModel.DefaultValueAttribute> y proporcionar el valor predeterminado al constructor de clases de atributos en su lugar.  Cualquiera de estos mecanismos habilita las siguientes características en el diseñador:  
  
-   La propiedad ofrece una indicación visual en el explorador de propiedades si se ha modificado su valor predeterminado.  
  
-   El usuario puede hacer clic con el botón secundario del mouse en la propiedad y elegir **Restablecer** para restablecer el valor predeterminado de la propiedad.  
  
-   El diseñador genera código más eficiente.  
  
    > [!NOTE]
    >  Aplique <xref:System.ComponentModel.DefaultValueAttribute> o proporcione los métodos `Reset`*nombreDePropiedad* y `ShouldSerialize`*nombreDePropiedad*.  No utilice ambos.  
  
 El método `Reset`*nombreDePropiedad* establece una propiedad en su valor predeterminado, como se muestra en el fragmento de código siguiente.  
  
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
>  Si una propiedad no posee un método `Reset`, no está marcada con un atributo <xref:System.ComponentModel.DefaultValueAttribute> y no se le ha asignado un valor predeterminado en su declaración, la opción `Reset` de dicha propiedad estará deshabilitada en el menú contextual de la ventana **Propiedades** del Diseñador de Windows Forms de [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
 Los diseñadores como [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] utilizan el método `ShouldSerialize`*nombreDePropiedad* para comprobar si una propiedad ha cambiado respecto a su valor predeterminado, escribir código en el formulario únicamente si ha cambiado la propiedad y, de esta manera, permitir una generación de código más eficiente.  Por ejemplo:  
  
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
  
 En este caso, aunque el valor de la variable privada a la que tiene acceso la propiedad `MyFont` sea `null`, el explorador de la propiedad no muestra `null`; en su lugar, muestra la propiedad <xref:System.Windows.Forms.Control.Font%2A> del primario, si no es `null` o el valor <xref:System.Windows.Forms.Control.Font%2A> predeterminado definido en <xref:System.Windows.Forms.Control>.  De este modo el valor predeterminado de `MyFont` no se puede establecer simplemente ni se puede aplicar un atributo <xref:System.ComponentModel.DefaultValueAttribute> a esta propiedad.  En su lugar, se deben implementar los métodos `ShouldSerialize` y `Reset` para la propiedad `MyFont`.  
  
## Vea también  
 [Propiedades de los controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [Definir una propiedad](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)   
 [Eventos de cambio de propiedades](../../../../docs/framework/winforms/controls/property-changed-events.md)