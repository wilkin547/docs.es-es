---
title: "Definir una propiedad en los controles de formularios Windows Forms | Microsoft Docs"
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
  - "controles personalizados [Windows Forms], definir propiedades en código"
  - "propiedades [Windows Forms], definir en código"
ms.assetid: c2eb8277-a842-4d99-89a9-647b901a0434
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Definir una propiedad en los controles de formularios Windows Forms
Para ver información general de las propiedades, vea [Properties Overview](../Topic/Properties%20Overview.md).  Al definir una propiedad, conviene tener presente una serie de consideraciones importantes:  
  
-   Se deben aplicar atributos a las propiedades que se definan.  Los atributos especifican cómo debe mostrar el diseñador una propiedad.  Para obtener información detallada, vea [Design\-Time Attributes for Components](../Topic/Design-Time%20Attributes%20for%20Components.md).  
  
-   Si la modificación de una propiedad afecta a la apariencia visual del control, se debe llamar al método <xref:System.Windows.Forms.Control.Invalidate%2A> \(que el control hereda de <xref:System.Windows.Forms.Control>\) desde el descriptor de acceso `set`.  <xref:System.Windows.Forms.Control.Invalidate%2A> llama a su vez al método <xref:System.Windows.Forms.Control.OnPaint%2A>, que vuelve a dibujar el control.  Si se realizan muchas llamadas a <xref:System.Windows.Forms.Control.Invalidate%2A>, se obtiene como resultado una llamada única a <xref:System.Windows.Forms.Control.OnPaint%2A> para mayor eficiencia.  
  
-   La biblioteca de clases de .NET Framework proporciona convertidores de tipos para los tipos de datos habituales, como enteros, decimales, valores booleanos y otros.  En general, los convertidores de tipos tienen por objeto proporcionar conversiones de cadena a valor \(de datos de cadena a otros tipos de datos\).  Los tipos de datos habituales están asociados a convertidores de tipos predeterminados que convierten valores en cadenas, y las cadenas en los tipos de datos correspondientes.  Si se define una propiedad que constituye un tipo de datos personalizado \(es decir no estándar\), se deberá aplicar un atributo que especifique el convertidor de tipos que se asociará a dicha propiedad.  También se puede utilizar un atributo para asociar un editor de tipos de interfaz de usuario personalizado a una propiedad.  Los editores de tipos de interfaz de usuario proporcionan una interfaz de usuario para editar una propiedad o un tipo de datos.  Los selectores de colores son un ejemplo de editor de tipos de interfaz de usuario.  Al final de este tema se muestran varios ejemplos de atributos.  
  
    > [!NOTE]
    >  Si no está disponible un convertidor de tipos o un editor de tipos de interfaz de usuario para la propiedad personalizada, se puede implementar uno, como se describe en [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md).  
  
 El siguiente fragmento de código define una propiedad personalizada denominada `EndColor` del control personalizado `FlashTrackBar`.  
  
```vb  
Public Class FlashTrackBar  
   Inherits Control  
   ...  
   ' Private data member that backs the EndColor property.  
   Private _endColor As Color = Color.LimeGreen  
  
   ' The Category attribute tells the designer to display  
   ' it in the Flash grouping.   
   ' The Description attribute provides a description of  
   ' the property.   
   <Category("Flash"), _  
   Description("The ending color of the bar.")>  _  
   Public Property EndColor() As Color  
      ' The public property EndColor accesses _endColor.  
      Get  
         Return _endColor  
      End Get  
      Set  
         _endColor = value  
         If Not (baseBackground Is Nothing) And showGradient Then  
            baseBackground.Dispose()  
            baseBackground = Nothing  
         End If  
         ' The Invalidate method calls the OnPaint method, which redraws    
         ' the control.  
         Invalidate()  
      End Set  
   End Property  
   ...  
End Class  
  
```  
  
```csharp  
public class FlashTrackBar : Control {  
   ...  
   // Private data member that backs the EndColor property.  
   private Color endColor = Color.LimeGreen;  
   // The Category attribute tells the designer to display  
   // it in the Flash grouping.   
   // The Description attribute provides a description of  
   // the property.   
   [  
   Category("Flash"),  
   Description("The ending color of the bar.")  
   ]  
   // The public property EndColor accesses endColor.  
   public Color EndColor {  
      get {  
         return endColor;  
      }  
      set {  
         endColor = value;  
         if (baseBackground != null && showGradient) {  
            baseBackground.Dispose();  
            baseBackground = null;  
         }  
         // The Invalidate method calls the OnPaint method, which redraws   
         // the control.  
         Invalidate();  
      }  
   }  
   ...  
}  
```  
  
 El fragmento de código siguiente asocia un convertidor de tipos y un editor de tipos de interfaz de usuario a la propiedad `Value`.  En este caso, `Value` es un entero y cuenta con un convertidor de tipos predeterminado, pero el atributo <xref:System.ComponentModel.TypeConverterAttribute> aplica un convertidor de tipos personalizado \(`FlashTrackBarValueConverter`\) que permite al diseñador mostrarlo como un porcentaje.  El editor de tipos de interfaz de usuario, `FlashTrackBarValueEditor`, permite que el porcentaje se muestre visualmente.  Este ejemplo también muestra cómo el convertidor de tipos o el editor especificado por el atributo <xref:System.ComponentModel.TypeConverterAttribute> o <xref:System.ComponentModel.EditorAttribute> reemplaza al convertidor predeterminado.  
  
```vb  
<Category("Flash"), _  
TypeConverter(GetType(FlashTrackBarValueConverter)), _  
Editor(GetType(FlashTrackBarValueEditor), _  
GetType(UITypeEditor)), _  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")>  _  
Public ReadOnly Property Value() As Integer  
...  
End Property  
  
```  
  
```csharp  
[  
Category("Flash"),   
TypeConverter(typeof(FlashTrackBarValueConverter)),  
Editor(typeof(FlashTrackBarValueEditor), typeof(UITypeEditor)),  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")  
]  
public int Value {  
...  
}  
```  
  
## Vea también  
 [Propiedades de los controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [Definir valores predeterminados con los métodos ShouldSerialize y Reset](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)   
 [Eventos de cambio de propiedades](../../../../docs/framework/winforms/controls/property-changed-events.md)   
 [Atributos en controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)