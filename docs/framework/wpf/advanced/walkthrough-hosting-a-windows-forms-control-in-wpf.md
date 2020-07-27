---
title: Hospedar un control de Windows Forms en WPF
description: Aprenda a hospedar Windows Forms controles en Windows Presentation Foundation, que ya proporciona muchos controles con un conjunto de características enriquecidas.
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: ec67cf9fabaa5b7aadbb2a3c21ebf8dd828ee20f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164971"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a>Tutorial: Hospedar un control de formularios Windows Forms en WPF

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona numerosos controles con un conjunto de características enriquecidas. Sin embargo, a veces es posible que desee usar controles de Windows Forms en las [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] páginas. Por ejemplo, puede tener una inversión sustancial en los controles de Windows Forms existentes o puede tener un control Windows Forms que proporcione una funcionalidad única.

En este tutorial se muestra cómo hospedar un <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control de Windows Forms en una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] página mediante código.

Para obtener una lista de código completa de las tareas que se muestran en este tutorial, vea [hospedar un control de Windows Forms en el ejemplo de WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF).

## <a name="prerequisites"></a>Requisitos previos

Necesita Visual Studio para completar este tutorial.

## <a name="hosting-the-windows-forms-control"></a>Hospedar el control de Windows Forms

### <a name="to-host-the-maskedtextbox-control"></a>Para hospedar el control MaskedTextBox

1. Cree un proyecto de aplicación de WPF denominado `HostingWfInWpf` .

2. Agregue referencias a los ensamblados siguientes.

    - WindowsFormsIntegration

    - System.Windows.Forms

3. Abra MainWindow. XAML en el diseñador de WPF.

4. Asigne un nombre al <xref:System.Windows.Controls.Grid> elemento `grid1` .

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. En Vista de diseño o en la vista XAML, seleccione el <xref:System.Windows.Window> elemento.

6. En el ventana Propiedades, haga clic en la pestaña **eventos** .

7. Haga doble clic en el <xref:System.Windows.FrameworkElement.Loaded> evento.

8. Inserte el código siguiente para controlar el <xref:System.Windows.FrameworkElement.Loaded> evento.

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. En la parte superior del archivo, agregue la siguiente `Imports` `using` instrucción o.

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. Presione **F5** para compilar y ejecutar la aplicación.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un control de Windows Forms en WPF mediante XAML](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Controles de Windows Forms y controles equivalentes de WPF](windows-forms-controls-and-equivalent-wpf-controls.md)
- [Hosting a Windows Forms Control in WPF Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF) (Ejemplo de cómo hospedar un control de Windows Forms en WPF)
