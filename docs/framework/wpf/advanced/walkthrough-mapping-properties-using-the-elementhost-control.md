---
title: 'Tutorial: Asignar propiedades mediante el uso del Control ElementHost'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: bb418b725afd0c38a39e42e50511147d0f616059
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623227"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a>Tutorial: Asignar propiedades mediante el uso del Control ElementHost

En este tutorial se muestra cómo usar el <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> propiedad para la asignación [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] propiedades a las propiedades correspondientes en una hospedada [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elemento.

Las tareas ilustradas en este tutorial incluyen:

-   Crear el proyecto.

-   Definir una nueva asignación de propiedades.

-   Quitar una asignación de propiedades predeterminada.

-   Extender una asignación de propiedades predeterminada.

Para obtener una lista de código completo de las tareas ilustradas en este tutorial, vea [asignar propiedades mediante el ejemplo del Control ElementHost](https://go.microsoft.com/fwlink/?LinkID=160018).

Cuando haya terminado, podrá asignar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] propiedades correspondiente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades en un elemento hospedado.

## <a name="prerequisites"></a>Requisitos previos

Necesita los componentes siguientes para completar este tutorial:

-   Visual Studio 2017

## <a name="creating-the-project"></a>Crear el proyecto

### <a name="to-create-the-project"></a>Para crear el proyecto

1.  Crear un **aplicación de Windows Forms** proyecto denominado `PropertyMappingWithElementHost`.

2.  En **el Explorador de soluciones**, agregue referencias a los siguientes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ensamblados.

    -   PresentationCore

    -   PresentationFramework

    -   WindowsBase

    -   WindowsFormsIntegration

3.  Copie el código siguiente en la parte superior de la `Form1` archivo de código.

     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4.  Abra `Form1` en el Diseñador de Windows Forms. Haga doble clic en el formulario para agregar un controlador de eventos para el <xref:System.Windows.Forms.Form.Load> eventos.

5.  Vuelva al diseñador de Windows Forms y agregue un controlador de eventos para el formulario <xref:System.Windows.Forms.Control.Resize> eventos. Para obtener más información, vea [Cómo: Crear controladores de eventos mediante el diseñador](https://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).

6.  Declarar un <xref:System.Windows.Forms.Integration.ElementHost> campo el `Form1` clase.

     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a>Definir nuevas asignaciones de propiedad

El <xref:System.Windows.Forms.Integration.ElementHost> control proporciona predeterminada varias asignaciones de propiedades. Agregar una nueva asignación de propiedad mediante una llamada a la <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> método en el <xref:System.Windows.Forms.Integration.ElementHost> del control <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.

### <a name="to-define-new-property-mappings"></a>Para definir nuevas asignaciones de propiedad

1.  Copie el código siguiente en la definición para el `Form1` clase.

     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     El `AddMarginMapping` método agrega una nueva asignación para el <xref:System.Windows.Forms.Control.Margin%2A> propiedad.

     El `OnMarginChange` método traduce el <xref:System.Windows.Forms.Control.Margin%2A> propiedad a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> propiedad.

2.  Copie el código siguiente en la definición para el `Form1` clase.

     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     El `AddRegionMapping` método agrega una nueva asignación para el <xref:System.Windows.Forms.Control.Region%2A> propiedad.

     El `OnRegionChange` método traduce el <xref:System.Windows.Forms.Control.Region%2A> propiedad a la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> propiedad.

     El `Form1_Resize` método controla el formulario <xref:System.Windows.Forms.Control.Resize> eventos y ajusta el tamaño de la región de recorte para adaptarse al elemento hospedado.

## <a name="removing-a-default-property-mapping"></a>Quitar una asignación de propiedades predeterminada

Quitar una asignación de propiedades predeterminada llamando el <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> método en el <xref:System.Windows.Forms.Integration.ElementHost> del control <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.

### <a name="to-remove-a-default-property-mapping"></a>Para quitar una asignación de propiedades predeterminada

-   Copie el código siguiente en la definición para el `Form1` clase.

     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     El `RemoveCursorMapping` método elimina la asignación predeterminada para el <xref:System.Windows.Forms.Control.Cursor%2A> propiedad.

## <a name="extending-a-default-property-mapping"></a>Extender una asignación de propiedades predeterminada

Puede usar una asignación de propiedades predeterminada y extenderla con su propia asignación.

### <a name="to-extend-a-default-property-mapping"></a>Para extender una asignación de propiedades predeterminada

-   Copie el código siguiente en la definición para el `Form1` clase.

     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     El `ExtendBackColorMapping` método agrega un traductor de propiedad personalizada existente <xref:System.Windows.Forms.Control.BackColor%2A> asignación de propiedades.

     El `OnBackColorChange` método asigna una imagen específica para el control hospedado <xref:System.Windows.Controls.Control.Background%2A> propiedad. El `OnBackColorChange` se llama al método después de aplica la asignación de propiedades predeterminada.

## <a name="initialize-your-property-mappings"></a>Inicializar las asignaciones de propiedades

1.  Copie el código siguiente en la definición para el `Form1` clase.

     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     El `Form1_Load` método controla el <xref:System.Windows.Forms.Form.Load> eventos y realiza la inicialización siguiente.

    -   Crea un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> elemento.

    -   Llama a los métodos definidos anteriormente en el tutorial para configurar las asignaciones de propiedades.

    -   Asigna los valores iniciales a las propiedades asignadas.

2.  Presione F5 para compilar y ejecutar la aplicación.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Asignación de propiedades en formularios Windows Forms y WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un Control compuesto de WPF en Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)