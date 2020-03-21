---
title: Definir propiedades de control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [Windows Forms], defining in code
- custom controls [Windows Forms], defining properties in code
ms.assetid: c2eb8277-a842-4d99-89a9-647b901a0434
ms.openlocfilehash: 7223f8c88bee4ee9c1db621cc39bbcf70d0c4589
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182372"
---
# <a name="defining-a-property-in-windows-forms-controls"></a>Definir una propiedad en los controles de formularios Windows Forms
Para información general de propiedades, vea [Información general sobre propiedades](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)). Hay que hacer algunas consideraciones importantes al definir una propiedad:  
  
- Debe aplicar atributos a las propiedades que defina. Atributos especifican cómo debe mostrar una propiedad el diseñador. Para más información, consulte [Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)) (Atributos en tiempo de diseño para componentes).  
  
- Si cambiar la propiedad afecta a la <xref:System.Windows.Forms.Control.Invalidate%2A> presentación visual del control, <xref:System.Windows.Forms.Control>llame `set` al método (que el control hereda del ) del descriptor de acceso. <xref:System.Windows.Forms.Control.Invalidate%2A>a su <xref:System.Windows.Forms.Control.OnPaint%2A> vez llama al método, que redibuja el control. Múltiples <xref:System.Windows.Forms.Control.Invalidate%2A> llamadas para dar <xref:System.Windows.Forms.Control.OnPaint%2A> lugar a una sola llamada a la eficiencia.  
  
- La biblioteca de clases de .NET Framework proporciona convertidores de tipos para tipos de datos comunes tales como enteros, números decimales, valores booleanos y otros. La finalidad de un convertidor de tipos suele ser facilitar conversiones de valor de cadena (de datos de cadena a otros tipos de datos). Los tipos de datos comunes se asocian a convertidores de tipos predeterminados que convierten los valores en cadenas y las cadenas en los tipos de datos adecuados. Si se define una propiedad que consiste en un tipo de datos personalizado (es decir, no estándar), tendrá que aplicar un atributo que especifique el convertidor de tipos que se va a asociar a esa propiedad. También puede usarse un atributo que asocie un editor de tipos de interfaz de usuario personalizado a una propiedad. Un editor de tipos de interfaz de usuario ofrece una interfaz de usuario para editar una propiedad o un tipo de datos. Un ejemplo de editor de tipos de interfaz de usuario es un selector de colores. Al final de este tema se dan ejemplos de atributos.  
  
    > [!NOTE]
    > Si no dispone de un convertidor de tipos o de un editor de tipos de interfaz de usuario para la propiedad personalizada, puede implementar una, tal y como se describe en [Ampliar compatibilidad en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).  
  
 En el fragmento de código siguiente se define una propiedad personalizada denominada `EndColor` para el control personalizado `FlashTrackBar`.  
  
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
  
 El fragmento de código siguiente asocia un convertidor de tipos y un editor de tipos de interfaz de usuario a la propiedad `Value`. En este `Value` caso es un entero y tiene <xref:System.ComponentModel.TypeConverterAttribute> un convertidor de`FlashTrackBarValueConverter`tipos predeterminado, pero el atributo aplica un convertidor de tipos personalizado ( ) que permite al diseñador mostrarlo como un porcentaje. El editor de tipos de interfaz de usuario, `FlashTrackBarValueEditor`, permite que el porcentaje se muestre visualmente. Este ejemplo también muestra que el convertidor <xref:System.ComponentModel.TypeConverterAttribute> de <xref:System.ComponentModel.EditorAttribute> tipos o editor especificado por el atributo o reemplaza el convertidor predeterminado.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Propiedades de los controles de Windows Forms](properties-in-windows-forms-controls.md)
- [Definir valores predeterminados con los métodos ShouldSerialize y Reset](defining-default-values-with-the-shouldserialize-and-reset-methods.md)
- [Eventos de cambio de propiedades](property-changed-events.md)
- [Atributos en controles de Windows Forms](attributes-in-windows-forms-controls.md)
