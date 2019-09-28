---
title: 'Tutorial: Hospedar un control compuesto 3D de WPF en formularios Windows Forms'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: a35f2b4062edb18914c55046a69dcd9b8825d778
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353840"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a>Tutorial: Hospedar un control compuesto 3D de WPF en formularios Windows Forms

En este tutorial se muestra cómo se puede crear un control compuesto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y cómo hospedarlo en controles [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y formularios mediante el control <xref:System.Windows.Forms.Integration.ElementHost>.

En este tutorial, implementará un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> que contiene dos controles secundarios. El <xref:System.Windows.Controls.UserControl> muestra un cono tridimensional (3D). La representación de objetos 3D es mucho más fácil con el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que con [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Por lo tanto, tiene sentido hospedar una clase [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> para crear gráficos 3D en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].

Las tareas ilustradas en este tutorial incluyen:

- Crear el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.

- Crear el proyecto de host de Windows Forms.

- Hospedar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.

## <a name="prerequisites"></a>Requisitos previos

Necesita los componentes siguientes para completar este tutorial:

- Visual Studio 2017

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a>Crear el UserControl

1. Cree un proyecto de **biblioteca de controles de usuario de WPF** denominado `HostingWpfUserControlInWf`.

2. Abra UserControl1. XAML en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].

3. Reemplace el código generado por el código siguiente:

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     Este código define un <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> que contiene dos controles secundarios. El primer control secundario es un control <xref:System.Windows.Controls.Label?displayProperty=nameWithType>; el segundo es un control <xref:System.Windows.Controls.Viewport3D> que muestra un cono 3D.

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a>Crear el proyecto de host

1. Agregue un proyecto de **Windows Forms App (.NET Framework)** denominado `WpfUserControlHost` a la solución.

2. En **Explorador de soluciones**, agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration. dll.

3. Agregue referencias a los siguientes ensamblados [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:

    - PresentationCore

    - PresentationFramework

    - WindowsBase

4. Agregue una referencia al proyecto `HostingWpfUserControlInWf`.

5. En Explorador de soluciones, establezca el proyecto `WpfUserControlHost` como proyecto de inicio.

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a>Hospede el UserControl

1. En el Diseñador de Windows Forms, abra Form1.

2. En el ventana Propiedades, haga clic en **eventos**y, a continuación, haga doble clic en el evento <xref:System.Windows.Forms.Form.Load> para crear un controlador de eventos.

     El editor de código se abre en el controlador de eventos `Form1_Load` recién generado.

3. Reemplace el código de Form1.cs por el código siguiente.

     El controlador de eventos `Form1_Load` crea una instancia de `UserControl1` y agrega trabajará a la colección de controles secundarios del control <xref:System.Windows.Forms.Integration.ElementHost>. El control <xref:System.Windows.Forms.Integration.ElementHost> se agrega a la colección de controles secundarios del formulario.

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. Presione **F5** para compilar y ejecutar la aplicación.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un control compuesto de WPF en Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Tutorial: Hospedar un control compuesto de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Hospedar un control compuesto de WPF en Windows Forms ejemplo](https://go.microsoft.com/fwlink/?LinkID=160001)
