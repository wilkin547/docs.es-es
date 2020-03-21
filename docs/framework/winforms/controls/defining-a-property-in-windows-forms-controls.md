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
# <a name="defining-a-property-in-windows-forms-controls"></a><span data-ttu-id="9ab9c-102">Definir una propiedad en los controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ab9c-102">Defining a Property in Windows Forms Controls</span></span>
<span data-ttu-id="9ab9c-103">Para información general de propiedades, vea [Información general sobre propiedades](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="9ab9c-103">For an overview of properties, see [Properties Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)).</span></span> <span data-ttu-id="9ab9c-104">Hay que hacer algunas consideraciones importantes al definir una propiedad:</span><span class="sxs-lookup"><span data-stu-id="9ab9c-104">There are a few important considerations when defining a property:</span></span>  
  
- <span data-ttu-id="9ab9c-105">Debe aplicar atributos a las propiedades que defina.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-105">You must apply attributes to the properties you define.</span></span> <span data-ttu-id="9ab9c-106">Atributos especifican cómo debe mostrar una propiedad el diseñador.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-106">Attributes specify how the designer should display a property.</span></span> <span data-ttu-id="9ab9c-107">Para más información, consulte [Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)) (Atributos en tiempo de diseño para componentes).</span><span class="sxs-lookup"><span data-stu-id="9ab9c-107">For details, see [Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span></span>  
  
- <span data-ttu-id="9ab9c-108">Si cambiar la propiedad afecta a la <xref:System.Windows.Forms.Control.Invalidate%2A> presentación visual del control, <xref:System.Windows.Forms.Control>llame `set` al método (que el control hereda del ) del descriptor de acceso.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-108">If changing the property affects the visual display of the control, call the <xref:System.Windows.Forms.Control.Invalidate%2A> method (that your control inherits from <xref:System.Windows.Forms.Control>) from the `set` accessor.</span></span> <span data-ttu-id="9ab9c-109"><xref:System.Windows.Forms.Control.Invalidate%2A>a su <xref:System.Windows.Forms.Control.OnPaint%2A> vez llama al método, que redibuja el control.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-109"><xref:System.Windows.Forms.Control.Invalidate%2A> in turn calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which redraws the control.</span></span> <span data-ttu-id="9ab9c-110">Múltiples <xref:System.Windows.Forms.Control.Invalidate%2A> llamadas para dar <xref:System.Windows.Forms.Control.OnPaint%2A> lugar a una sola llamada a la eficiencia.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-110">Multiple calls to <xref:System.Windows.Forms.Control.Invalidate%2A> result in a single call to <xref:System.Windows.Forms.Control.OnPaint%2A> for efficiency.</span></span>  
  
- <span data-ttu-id="9ab9c-111">La biblioteca de clases de .NET Framework proporciona convertidores de tipos para tipos de datos comunes tales como enteros, números decimales, valores booleanos y otros.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-111">The .NET Framework class library provides type converters for common data types such as integers, decimal numbers, Boolean values, and others.</span></span> <span data-ttu-id="9ab9c-112">La finalidad de un convertidor de tipos suele ser facilitar conversiones de valor de cadena (de datos de cadena a otros tipos de datos).</span><span class="sxs-lookup"><span data-stu-id="9ab9c-112">The purpose of a type converter is generally to provide string-to-value conversion (from string data to other data types).</span></span> <span data-ttu-id="9ab9c-113">Los tipos de datos comunes se asocian a convertidores de tipos predeterminados que convierten los valores en cadenas y las cadenas en los tipos de datos adecuados.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-113">Common data types are associated with default type converters that convert values into strings and strings into the appropriate data types.</span></span> <span data-ttu-id="9ab9c-114">Si se define una propiedad que consiste en un tipo de datos personalizado (es decir, no estándar), tendrá que aplicar un atributo que especifique el convertidor de tipos que se va a asociar a esa propiedad.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-114">If you define a property that is a custom (that is, nonstandard) data type, you will have to apply an attribute that specifies the type converter to associate with that property.</span></span> <span data-ttu-id="9ab9c-115">También puede usarse un atributo que asocie un editor de tipos de interfaz de usuario personalizado a una propiedad.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-115">You can also use an attribute to associate a custom UI type editor with a property.</span></span> <span data-ttu-id="9ab9c-116">Un editor de tipos de interfaz de usuario ofrece una interfaz de usuario para editar una propiedad o un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-116">A UI type editor provides a user interface for editing a property or data type.</span></span> <span data-ttu-id="9ab9c-117">Un ejemplo de editor de tipos de interfaz de usuario es un selector de colores.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-117">A color picker is an example of a UI type editor.</span></span> <span data-ttu-id="9ab9c-118">Al final de este tema se dan ejemplos de atributos.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-118">Examples of attributes are given at the end of this topic.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9ab9c-119">Si no dispone de un convertidor de tipos o de un editor de tipos de interfaz de usuario para la propiedad personalizada, puede implementar una, tal y como se describe en [Ampliar compatibilidad en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="9ab9c-119">If a type converter or a UI type editor is not available for your custom property, you can implement one as described in [Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).</span></span>  
  
 <span data-ttu-id="9ab9c-120">En el fragmento de código siguiente se define una propiedad personalizada denominada `EndColor` para el control personalizado `FlashTrackBar`.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-120">The following code fragment defines a custom property named `EndColor` for the custom control `FlashTrackBar`.</span></span>  
  
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
  
 <span data-ttu-id="9ab9c-121">El fragmento de código siguiente asocia un convertidor de tipos y un editor de tipos de interfaz de usuario a la propiedad `Value`.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-121">The following code fragment associates a type converter and a UI type editor with the property `Value`.</span></span> <span data-ttu-id="9ab9c-122">En este `Value` caso es un entero y tiene <xref:System.ComponentModel.TypeConverterAttribute> un convertidor de`FlashTrackBarValueConverter`tipos predeterminado, pero el atributo aplica un convertidor de tipos personalizado ( ) que permite al diseñador mostrarlo como un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-122">In this case `Value` is an integer and has a default type converter, but the <xref:System.ComponentModel.TypeConverterAttribute> attribute applies a custom type converter (`FlashTrackBarValueConverter`) that enables the designer to display it as a percentage.</span></span> <span data-ttu-id="9ab9c-123">El editor de tipos de interfaz de usuario, `FlashTrackBarValueEditor`, permite que el porcentaje se muestre visualmente.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-123">The UI type editor, `FlashTrackBarValueEditor`, allows the percentage to be displayed visually.</span></span> <span data-ttu-id="9ab9c-124">Este ejemplo también muestra que el convertidor <xref:System.ComponentModel.TypeConverterAttribute> de <xref:System.ComponentModel.EditorAttribute> tipos o editor especificado por el atributo o reemplaza el convertidor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9ab9c-124">This example also shows that the type converter or editor specified by the <xref:System.ComponentModel.TypeConverterAttribute> or <xref:System.ComponentModel.EditorAttribute> attribute overrides the default converter.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9ab9c-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ab9c-125">See also</span></span>

- [<span data-ttu-id="9ab9c-126">Propiedades de los controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ab9c-126">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="9ab9c-127">Definir valores predeterminados con los métodos ShouldSerialize y Reset</span><span class="sxs-lookup"><span data-stu-id="9ab9c-127">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](defining-default-values-with-the-shouldserialize-and-reset-methods.md)
- [<span data-ttu-id="9ab9c-128">Eventos de cambio de propiedades</span><span class="sxs-lookup"><span data-stu-id="9ab9c-128">Property-Changed Events</span></span>](property-changed-events.md)
- [<span data-ttu-id="9ab9c-129">Atributos en controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ab9c-129">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
