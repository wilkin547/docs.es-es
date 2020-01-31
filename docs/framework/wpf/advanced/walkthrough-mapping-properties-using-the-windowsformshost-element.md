---
title: 'Tutorial: Asignar propiedades mediante el uso del elemento WindowsFormsHost'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: c076937d6431adf1750793d47ece88dc82edf95c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794099"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a>Tutorial: Asignar propiedades mediante el uso del elemento WindowsFormsHost

En este tutorial se muestra cómo usar la propiedad <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> para asignar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades a las propiedades correspondientes de un control de Windows Forms hospedado.

Las tareas ilustradas en este tutorial incluyen:

- Crear el proyecto.

- Definir el diseño de la aplicación.

- Definir una nueva asignación de propiedades.

- Quitar una asignación de propiedades predeterminada.

- Reemplazar una asignación de propiedades predeterminada.

- Extender una asignación de propiedades predeterminada.

Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea [asignar propiedades mediante el ejemplo de elemento WindowsFormsHost](https://go.microsoft.com/fwlink/?LinkID=160019).

Cuando haya terminado, podrá asignar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades a las propiedades correspondientes de un control de Windows Forms hospedado.

## <a name="prerequisites"></a>Requisitos previos

Necesita los componentes siguientes para completar este tutorial:

- Visual Studio 2017

## <a name="create-and-set-up-the-project"></a>Crear y configurar el proyecto

1. Cree un proyecto de **aplicación de WPF** denominado `PropertyMappingWithWfhSample`.

2. En **Explorador de soluciones**, agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration. dll.

3. En **Explorador de soluciones**, agregue referencias a los ensamblados System. Drawing y System. Windows. Forms.

## <a name="defining-the-application-layout"></a>Definir el diseño de la aplicación

La aplicación basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]utiliza el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> para hospedar un control Windows Forms.

### <a name="to-define-the-application-layout"></a>Para definir el diseño de la aplicación

1. Abra Window1. XAML en el diseñador de WPF.

2. Reemplace el código existente por el siguiente código.

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3. Abra Window1.xaml.cs en el Editor de código.

4. En la parte superior del archivo, importe los siguientes espacios de nombres.

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a>Definir una nueva asignación de propiedades

El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> proporciona varias asignaciones de propiedades predeterminadas. Agregue una nueva asignación de propiedad llamando al método <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> en la <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>del elemento de <xref:System.Windows.Forms.Integration.WindowsFormsHost>.

### <a name="to-define-a-new-property-mapping"></a>Para definir una nueva asignación de propiedades

- Copie el código siguiente en la definición de la clase `Window1`.

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     El método `AddClipMapping` agrega una nueva asignación para la propiedad <xref:System.Windows.UIElement.Clip%2A>.

     El método `OnClipChange` traduce la propiedad <xref:System.Windows.UIElement.Clip%2A> a la propiedad Windows Forms<xref:System.Windows.Forms.Control.Region%2A>.

     El método `Window1_SizeChanged` controla el evento de <xref:System.Windows.FrameworkElement.SizeChanged> de la ventana y ajusta el tamaño de la región de recorte para ajustarla a la ventana de la aplicación.

## <a name="removing-a-default-property-mapping"></a>Quitar una asignación de propiedades predeterminada

Quitar una asignación de propiedades predeterminada llamando al método <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> en la <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>del elemento de <xref:System.Windows.Forms.Integration.WindowsFormsHost>.

### <a name="to-remove-a-default-property-mapping"></a>Para quitar una asignación de propiedades predeterminada

- Copie el código siguiente en la definición de la clase `Window1`.

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     El método `RemoveCursorMapping` elimina la asignación predeterminada para la propiedad <xref:System.Windows.FrameworkElement.Cursor%2A>.

## <a name="replacing-a-default-property-mapping"></a>Reemplazar una asignación de propiedades predeterminada

Reemplace una asignación de propiedades predeterminada quitando la asignación predeterminada y llamando al método <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> en el <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.

### <a name="to-replace-a-default-property-mapping"></a>Para reemplazar una asignación de propiedades predeterminada

- Copie el código siguiente en la definición de la clase `Window1`.

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     El método `ReplaceFlowDirectionMapping` reemplaza la asignación predeterminada para la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A>.

     El método `OnFlowDirectionChange` traduce la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> a la propiedad Windows Forms<xref:System.Windows.Forms.Control.RightToLeft%2A>.

     El método `cb_CheckedChanged` controla el evento de <xref:System.Windows.Forms.CheckBox.CheckedChanged> en el control de <xref:System.Windows.Forms.CheckBox>. Asigna la propiedad <xref:System.Windows.FrameworkElement.FlowDirection%2A> basada en el valor de la propiedad <xref:System.Windows.Forms.CheckBox.CheckState%2A>

## <a name="extending-a-default-property-mapping"></a>Extender una asignación de propiedades predeterminada

Puede usar una asignación de propiedades predeterminada y extenderla con su propia asignación.

### <a name="to-extend-a-default-property-mapping"></a>Para extender una asignación de propiedades predeterminada

- Copie el código siguiente en la definición de la clase `Window1`.

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     El método `ExtendBackgroundMapping` agrega un traductor de propiedades personalizado a la asignación de propiedades de <xref:System.Windows.Controls.Control.Background%2A> existente.

     El método `OnBackgroundChange` asigna una imagen específica a la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A> del control hospedado. Se llama al método `OnBackgroundChange` después de aplicar la asignación de propiedad predeterminada.

## <a name="initializing-your-property-mappings"></a>Inicializar las asignaciones de propiedades

Configure las asignaciones de propiedades mediante una llamada a los métodos descritos anteriormente en el controlador de eventos <xref:System.Windows.FrameworkElement.Loaded>.

### <a name="to-initialize-your-property-mappings"></a>Para inicializar las asignaciones de propiedades

1. Copie el código siguiente en la definición de la clase `Window1`.

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     El método `WindowLoaded` controla el evento <xref:System.Windows.FrameworkElement.Loaded> y realiza la inicialización siguiente.

    - Crea un control de<xref:System.Windows.Forms.CheckBox> de Windows Forms.

    - Llama a los métodos definidos anteriormente en el tutorial para configurar las asignaciones de propiedades.

    - Asigna los valores iniciales a las propiedades asignadas.

2. Presione **F5** para compilar y ejecutar la aplicación. Haga clic en la casilla para ver el efecto de la asignación de <xref:System.Windows.FrameworkElement.FlowDirection%2A>. Al hacer clic en la casilla, el diseño invierte su orientación de izquierda a derecha.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md)
- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un control de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
