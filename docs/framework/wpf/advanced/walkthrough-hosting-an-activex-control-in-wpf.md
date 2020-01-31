---
title: Hospedar un control ActiveX en WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
ms.openlocfilehash: 4ca40c0f6e62fd413e7f305649c5c01ddc152b2a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794144"
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a>Tutorial: Hospedar un control ActiveX en WPF
Para habilitar la interacción mejorada con los exploradores, puede usar los controles ActiveX de Microsoft en la aplicación basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. En este tutorial se muestra cómo puede hospedar el Media Player de Microsoft Windows como un control en una página de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

 Las tareas ilustradas en este tutorial incluyen:

- Crear el proyecto.

- Crear el control ActiveX.

- Hospedar el control ActiveX en una página de WPF.

 Cuando haya completado este tutorial, aprenderá a usar los controles ActiveX de Microsoft en la aplicación basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

## <a name="prerequisites"></a>Requisitos previos
 Necesita los componentes siguientes para completar este tutorial:

- Microsoft Windows Media Player instalado en el equipo donde está instalado Visual Studio.

- Visual Studio 2010.

## <a name="creating-the-project"></a>Crear el proyecto

### <a name="to-create-and-set-up-the-project"></a>Para crear y configurar el proyecto

1. Cree un proyecto de aplicación de WPF denominado `HostingAxInWpf`.

2. Agregue un proyecto de biblioteca de controles Windows Forms a la solución y asigne al proyecto el nombre `WmpAxLib`.

3. En el proyecto WmpAxLib, agregue una referencia al ensamblado de Windows Media Player, que se denomina wmp. dll.

4. Abra el **cuadro de herramientas**.

5. Haga clic con el botón secundario en el **cuadro de herramientas**y haga clic en **elegir elementos**.

6. Haga clic en la pestaña **componentes com** , seleccione el control **Windows Media Player** y, a continuación, haga clic en **Aceptar**.

     El control Media Player de Windows se agrega al **cuadro de herramientas**.

7. En Explorador de soluciones, haga clic con el botón secundario en el archivo **UserControl1** y, a continuación, haga clic en **cambiar nombre**.

8. Cambie el nombre a `WmpAxControl.vb` o `WmpAxControl.cs`, según el lenguaje.

9. Si se le pide que cambie el nombre de todas las referencias, haga clic en **sí**.

## <a name="creating-the-activex-control"></a>Crear el control ActiveX
Visual Studio genera automáticamente una clase contenedora <xref:System.Windows.Forms.AxHost> para un control ActiveX de Microsoft cuando el control se agrega a una superficie de diseño. En el procedimiento siguiente se crea un ensamblado administrado denominado AxInterop. WMPLib. dll.

### <a name="to-create-the-activex-control"></a>Para crear el control ActiveX

1. Abra WmpAxControl. vb o WmpAxControl.cs en el Diseñador de Windows Forms.

2. En el **cuadro de herramientas**, agregue el control Media Player de Windows a la superficie de diseño.

3. En el ventana Propiedades, establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control Media Player de Windows en <xref:System.Windows.Forms.DockStyle.Fill>.

4. Compile el proyecto de biblioteca de controles WmpAxLib.

## <a name="hosting-the-activex-control-on-a-wpf-page"></a>Hospedar el control ActiveX en una página de WPF

### <a name="to-host-the-activex-control"></a>Para hospedar el control ActiveX

1. En el proyecto HostingAxInWpf, agregue una referencia al ensamblado de interoperabilidad ActiveX generado.

     Este ensamblado se denomina AxInterop. WMPLib. dll y se agregó a la carpeta de depuración del proyecto WmpAxLib cuando importó el control Media Player de Windows.

2. Agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration. dll.

3. Agregue una referencia al ensamblado Windows Forms, que se denomina System. Windows. Forms. dll.

4. Abra MainWindow. XAML en el diseñador de WPF.

5. Asigne al elemento <xref:System.Windows.Controls.Grid> el nombre `grid1`.

     [!code-xaml[HostingAxInWpf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]

6. En Vista de diseño o en la vista XAML, seleccione el elemento <xref:System.Windows.Window>.

7. En el ventana Propiedades, haga clic en la pestaña **eventos** .

8. Haga doble clic en el evento <xref:System.Windows.FrameworkElement.Loaded>.

9. Inserte el código siguiente para controlar el evento <xref:System.Windows.FrameworkElement.Loaded>.

     Este código crea una instancia del control <xref:System.Windows.Forms.Integration.WindowsFormsHost> y agrega una instancia del control `AxWindowsMediaPlayer` como su elemento secundario.

     [!code-csharp[HostingAxInWpf#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. Presione F5 para compilar y ejecutar la aplicación.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
