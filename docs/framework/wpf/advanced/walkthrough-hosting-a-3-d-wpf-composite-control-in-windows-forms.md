---
title: 'Tutorial: Hospedar un control compuesto 3 D de WPF en Windows Forms'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: d84fe4314a162b4ed5d7d710964882dec85e8524
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501916"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a>Tutorial: Hospedar un control compuesto 3 D de WPF en Windows Forms

Este tutorial muestra cómo puede crear un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] compuesto controlar y hospedarlo en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles y formularios mediante el uso de la <xref:System.Windows.Forms.Integration.ElementHost> control.

En este tutorial, implementará un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> que contiene dos controles secundarios. La <xref:System.Windows.Controls.UserControl> muestra un cono tridimensional de (3D). Representar objetos 3D es mucho más fácil con la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que con [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Por lo tanto, tiene sentido para hospedar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> clase para crear gráficos en 3D en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].

Las tareas ilustradas en este tutorial incluyen:

-   Crear el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.

-   Crear el proyecto de host de Windows Forms.

-   Hospedar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.

## <a name="prerequisites"></a>Requisitos previos

Necesita los componentes siguientes para completar este tutorial:

-   Visual Studio 2017

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a>Crear la clase UserControl

1.  Crear un **biblioteca de controles de usuario de WPF** proyecto denominado `HostingWpfUserControlInWf`.

2.  Abra UserControl1.xaml en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].

3.  Reemplace el código generado por el código siguiente:

     [!code-xaml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     Este código define un <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> que contiene dos controles secundarios. El primer control secundario es un <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; el segundo es un <xref:System.Windows.Controls.Viewport3D> control que muestra un cono 3D.

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a>Crear el proyecto de host

1.  Agregar un **aplicación de WPF (.NET Framework)** proyecto denominado `WpfUserControlHost` a la solución. Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de WPF](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).

2.  En **el Explorador de soluciones**, agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration.dll.

3.  Agregue referencias a los siguientes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ensamblados:

    -   PresentationCore

    -   PresentationFramework

    -   WindowsBase

4.  Agregue una referencia al proyecto `HostingWpfUserControlInWf`.

5.  En el Explorador de soluciones, establezca el `WpfUserControlHost` proyecto para que sea el proyecto de inicio.

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a>Hospedar el control de usuario

1.  En el Diseñador de formularios de Windows, abra Form1.

2.  En la ventana Propiedades, haga clic en **eventos**y, a continuación, haga doble clic en el <xref:System.Windows.Forms.Form.Load> evento para crear un controlador de eventos.

     Se abre el Editor de código en la recién generado `Form1_Load` controlador de eventos.

3.  Reemplace el código en Form1.cs con el código siguiente.

     El `Form1_Load` controlador de eventos crea una instancia de `UserControl1` y agrega sus el <xref:System.Windows.Forms.Integration.ElementHost> colección de controles secundarios del control. El <xref:System.Windows.Forms.Integration.ElementHost> control se agrega a la colección del formulario de controles secundarios.

     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4.  Presione **F5** para compilar y ejecutar la aplicación.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Hospedar un Control compuesto de WPF en el ejemplo de Windows Forms](https://go.microsoft.com/fwlink/?LinkID=160001)