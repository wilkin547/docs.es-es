---
title: 'Tutorial: Asignar propiedades mediante el uso del elemento WindowsFormsHost'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f566d41ff1ffa07a2f52641ba05e48dfa604cfc9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a>Tutorial: Asignar propiedades mediante el uso del elemento WindowsFormsHost
En este tutorial se muestra cómo utilizar el <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> propiedad para asignar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades a las propiedades correspondientes en una hospedada [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear el proyecto.  
  
-   Definir el diseño de la aplicación.  
  
-   Definir una nueva asignación de propiedades.  
  
-   Quitar una asignación de propiedades predeterminada.  
  
-   Reemplazar una asignación de propiedades predeterminada.  
  
-   Extender una asignación de propiedades predeterminada.  
  
 Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea [propiedades de asignación mediante el ejemplo de elemento WindowsFormsHost](http://go.microsoft.com/fwlink/?LinkID=160019).  
  
 Cuando haya terminado, podrá asignar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades a las propiedades correspondientes en una hospedada [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-project"></a>Crear el proyecto  
  
#### <a name="to-create-and-set-up-the-project"></a>Para crear y configurar el proyecto  
  
1.  Cree un proyecto de aplicación WPF denominado `PropertyMappingWithWfhSample`.  
  
2.  En el Explorador de soluciones, agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration.dll.  
  
3.  En el Explorador de soluciones, agregue referencias a los ensamblados System.Drawing y System.Windows.Forms.  
  
## <a name="defining-the-application-layout"></a>Definir el diseño de la aplicación  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-basado en aplicación usa el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento para hospedar un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.  
  
#### <a name="to-define-the-application-layout"></a>Para definir el diseño de la aplicación  
  
1.  Abra Window1.xaml en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
2.  Reemplace el código existente por el siguiente código.  
  
     [!code-xaml[PropertyMappingWithWfhSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]  
  
3.  Abra Window1.xaml.cs en el Editor de código.  
  
4.  En la parte superior del archivo, importe los siguientes espacios de nombres.  
  
     [!code-csharp[PropertyMappingWithWfhSample#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]  
  
## <a name="defining-a-new-property-mapping"></a>Definir una nueva asignación de propiedades  
 El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento proporciona predeterminado varias asignaciones de propiedad. Agregar una nueva asignación de propiedad mediante una llamada a la <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> método en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-define-a-new-property-mapping"></a>Para definir una nueva asignación de propiedades  
  
-   Copie el código siguiente en la definición de la `Window1` clase.  
  
     [!code-csharp[PropertyMappingWithWfhSample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]  
  
     El `AddClipMapping` método agrega una nueva asignación para el <xref:System.Windows.UIElement.Clip%2A> propiedad.  
  
     El `OnClipChange` método se traduce el <xref:System.Windows.UIElement.Clip%2A> propiedad a la [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.Region%2A> propiedad.  
  
     El `Window1_SizeChanged` método controla la ventana <xref:System.Windows.FrameworkElement.SizeChanged> eventos y cambia el tamaño de la región de recorte para ajustarse a la ventana de la aplicación.  
  
## <a name="removing-a-default-property-mapping"></a>Quitar una asignación de propiedades predeterminada  
 Quitar una asignación de propiedad predeterminada mediante una llamada a la <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> método en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-remove-a-default-property-mapping"></a>Para quitar una asignación de propiedades predeterminada  
  
-   Copie el código siguiente en la definición de la `Window1` clase.  
  
     [!code-csharp[PropertyMappingWithWfhSample#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]  
  
     El `RemoveCursorMapping` método elimina la asignación predeterminada para el <xref:System.Windows.FrameworkElement.Cursor%2A> propiedad.  
  
## <a name="replacing-a-default-property-mapping"></a>Reemplazar una asignación de propiedades predeterminada  
 Reemplazar una asignación de propiedad predeterminada mediante la eliminación de la asignación predeterminada y la llamada la <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> método en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.  
  
#### <a name="to-replace-a-default-property-mapping"></a>Para reemplazar una asignación de propiedades predeterminada  
  
-   Copie el código siguiente en la definición de la `Window1` clase.  
  
     [!code-csharp[PropertyMappingWithWfhSample#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]  
  
     El `ReplaceFlowDirectionMapping` método reemplaza la asignación predeterminada para el <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad.  
  
     El `OnFlowDirectionChange` método se traduce el <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad a la [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.RightToLeft%2A> propiedad.  
  
     El `cb_CheckedChanged` método controla la <xref:System.Windows.Forms.CheckBox.CheckedChanged> evento en el <xref:System.Windows.Forms.CheckBox> control. Asigna la <xref:System.Windows.FrameworkElement.FlowDirection%2A> propiedad basándose en el valor de la <xref:System.Windows.Forms.CheckBox.CheckState%2A> propiedad  
  
## <a name="extending-a-default-property-mapping"></a>Extender una asignación de propiedades predeterminada  
 Puede usar una asignación de propiedades predeterminada y extenderla con su propia asignación.  
  
#### <a name="to-extend-a-default-property-mapping"></a>Para extender una asignación de propiedades predeterminada  
  
-   Copie el código siguiente en la definición de la `Window1` clase.  
  
     [!code-csharp[PropertyMappingWithWfhSample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]  
  
     El `ExtendBackgroundMapping` método agrega un traductor de propiedades personalizadas a las existentes <xref:System.Windows.Controls.Control.Background%2A> asignación de propiedad.  
  
     El `OnBackgroundChange` método asigna una imagen específica para el control hospedado <xref:System.Windows.Forms.Control.BackgroundImage%2A> propiedad. El `OnBackgroundChange` método se llama después de aplica la asignación de propiedad predeterminada.  
  
## <a name="initializing-your-property-mappings"></a>Inicializar las asignaciones de propiedades  
 Configurar las asignaciones de propiedad llamando a los métodos descritos anteriormente el <xref:System.Windows.FrameworkElement.Loaded> controlador de eventos.  
  
#### <a name="to-initialize-your-property-mappings"></a>Para inicializar las asignaciones de propiedades  
  
1.  Copie el código siguiente en la definición de la `Window1` clase.  
  
     [!code-csharp[PropertyMappingWithWfhSample#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]  
  
     El `WindowLoaded` método controla la <xref:System.Windows.FrameworkElement.Loaded> eventos y realiza la inicialización siguiente.  
  
    -   Crea un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.CheckBox> control.  
  
    -   Llama a los métodos definidos anteriormente en el tutorial para configurar las asignaciones de propiedades.  
  
    -   Asigna los valores iniciales a las propiedades asignadas.  
  
2.  Presione F5 para compilar y ejecutar la aplicación. Haga clic en la casilla de verificación para ver el efecto de la <xref:System.Windows.FrameworkElement.FlowDirection%2A> asignación. Al hacer clic en la casilla, el diseño invierte su orientación de izquierda a derecha.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Asignación de propiedades en formularios Windows Forms y WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [WPF Designer](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Tutorial: Hospedar un control de Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
