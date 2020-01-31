---
title: 'Tutorial: Asignar propiedades mediante el uso del control ElementHost'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 7ff4ff607ab70b55cda1e2c4736ff773d4907a22
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794119"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a>Tutorial: Asignar propiedades mediante el uso del control ElementHost

En este tutorial se muestra cómo utilizar la propiedad <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> para asignar Windows Forms propiedades a las propiedades correspondientes de un elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedado.

Las tareas ilustradas en este tutorial incluyen:

- Crear el proyecto.

- Definir una nueva asignación de propiedades.

- Quitar una asignación de propiedades predeterminada.

- Extender una asignación de propiedades predeterminada.

Para obtener una lista de código completa de las tareas ilustradas en este tutorial, consulte [asignación de propiedades mediante el ejemplo de control ElementHost](https://go.microsoft.com/fwlink/?LinkID=160018).

Cuando haya terminado, podrá asignar Windows Forms propiedades a las propiedades [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] correspondientes en un elemento hospedado.

## <a name="prerequisites"></a>Requisitos previos

Necesita los componentes siguientes para completar este tutorial:

- Visual Studio 2017

## <a name="creating-the-project"></a>Crear el proyecto

### <a name="to-create-the-project"></a>Para crear el proyecto

1. Cree un proyecto de **aplicación de Windows Forms** denominado `PropertyMappingWithElementHost`.

2. En **Explorador de soluciones**, agregue referencias a los siguientes ensamblados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

    - PresentationCore

    - PresentationFramework

    - WindowsBase

    - WindowsFormsIntegration

3. Copie el código siguiente en la parte superior del archivo de código `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. Abra `Form1` en el Diseñador de Windows Forms. Haga doble clic en el formulario para agregar un controlador de eventos para el evento <xref:System.Windows.Forms.Form.Load>.

5. Vuelva al Diseñador de Windows Forms y agregue un controlador de eventos para el evento de <xref:System.Windows.Forms.Control.Resize> del formulario. Para obtener más información, vea [Cómo: crear controladores de eventos mediante el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).

6. Declare un campo <xref:System.Windows.Forms.Integration.ElementHost> en la clase `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a>Definir nuevas asignaciones de propiedades

El control <xref:System.Windows.Forms.Integration.ElementHost> proporciona varias asignaciones de propiedades predeterminadas. Agregue una nueva asignación de propiedad llamando al método <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> en el <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>del control <xref:System.Windows.Forms.Integration.ElementHost>.

### <a name="to-define-new-property-mappings"></a>Para definir nuevas asignaciones de propiedades

1. Copie el código siguiente en la definición de la clase `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     El método `AddMarginMapping` agrega una nueva asignación para la propiedad <xref:System.Windows.Forms.Control.Margin%2A>.

     El método `OnMarginChange` traduce la propiedad <xref:System.Windows.Forms.Control.Margin%2A> a la propiedad [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A>.

2. Copie el código siguiente en la definición de la clase `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     El método `AddRegionMapping` agrega una nueva asignación para la propiedad <xref:System.Windows.Forms.Control.Region%2A>.

     El método `OnRegionChange` traduce la propiedad <xref:System.Windows.Forms.Control.Region%2A> a la propiedad [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A>.

     El método `Form1_Resize` controla el evento de <xref:System.Windows.Forms.Control.Resize> del formulario y ajusta el tamaño de la región de recorte para que quepa en el elemento hospedado.

## <a name="removing-a-default-property-mapping"></a>Quitar una asignación de propiedades predeterminada

Quitar una asignación de propiedades predeterminada llamando al método <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> en el <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>del control <xref:System.Windows.Forms.Integration.ElementHost>.

### <a name="to-remove-a-default-property-mapping"></a>Para quitar una asignación de propiedades predeterminada

- Copie el código siguiente en la definición de la clase `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     El método `RemoveCursorMapping` elimina la asignación predeterminada para la propiedad <xref:System.Windows.Forms.Control.Cursor%2A>.

## <a name="extending-a-default-property-mapping"></a>Extender una asignación de propiedades predeterminada

Puede usar una asignación de propiedades predeterminada y extenderla con su propia asignación.

### <a name="to-extend-a-default-property-mapping"></a>Para extender una asignación de propiedades predeterminada

- Copie el código siguiente en la definición de la clase `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     El método `ExtendBackColorMapping` agrega un traductor de propiedades personalizado a la asignación de propiedades de <xref:System.Windows.Forms.Control.BackColor%2A> existente.

     El método `OnBackColorChange` asigna una imagen específica a la propiedad <xref:System.Windows.Controls.Control.Background%2A> del control hospedado. Se llama al método `OnBackColorChange` después de aplicar la asignación de propiedad predeterminada.

## <a name="initialize-your-property-mappings"></a>Inicializar las asignaciones de propiedades

1. Copie el código siguiente en la definición de la clase `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     El método `Form1_Load` controla el evento <xref:System.Windows.Forms.Form.Load> y realiza la inicialización siguiente.

    - Crea un elemento de <xref:System.Windows.Controls.Button> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

    - Llama a los métodos definidos anteriormente en el tutorial para configurar las asignaciones de propiedades.

    - Asigna los valores iniciales a las propiedades asignadas.

2. Presione F5 para compilar y ejecutar la aplicación.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md)
- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
