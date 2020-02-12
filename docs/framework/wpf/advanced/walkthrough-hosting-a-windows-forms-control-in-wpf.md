---
title: Hospedar un control de Windows Forms en WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: 2ed4e153a2513dc99d22a1538399156c138eb9e5
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123836"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a>Tutorial: Hospedar un control de Windows Forms en WPF

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona numerosos controles con un conjunto de características enriquecidas. Sin embargo, a veces es posible que desee usar controles de Windows Forms en las páginas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Por ejemplo, puede tener una inversión sustancial en los controles de Windows Forms existentes o puede tener un control Windows Forms que proporcione una funcionalidad única.

En este tutorial se muestra cómo hospedar un control de Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> en una página de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante el uso de código.

Para obtener una lista de código completa de las tareas que se muestran en este tutorial, vea [hospedar un control de Windows Forms en el ejemplo de WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF).

## <a name="prerequisites"></a>Prerequisites

Necesita Visual Studio para completar este tutorial.

## <a name="hosting-the-windows-forms-control"></a>Hospedar el control de Windows Forms

### <a name="to-host-the-maskedtextbox-control"></a>Para hospedar el control MaskedTextBox

1. Cree un proyecto de aplicación de WPF denominado `HostingWfInWpf`.

2. Agregue referencias a los ensamblados siguientes.

    - WindowsFormsIntegration

    - System.Windows.Forms

3. Abra MainWindow. XAML en el diseñador de WPF.

4. Asigne al elemento <xref:System.Windows.Controls.Grid> el nombre `grid1`.

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. En Vista de diseño o en la vista XAML, seleccione el elemento <xref:System.Windows.Window>.

6. En el ventana Propiedades, haga clic en la pestaña **eventos** .

7. Haga doble clic en el evento <xref:System.Windows.FrameworkElement.Loaded>.

8. Inserte el código siguiente para controlar el evento <xref:System.Windows.FrameworkElement.Loaded>.

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. En la parte superior del archivo, agregue la siguiente `Imports` o `using` instrucción.

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. Presione **F5** para compilar y ejecutar la aplicación.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un control de formularios Windows Forms en WPF mediante XAML](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Controles de Windows Forms y controles equivalentes de WPF](windows-forms-controls-and-equivalent-wpf-controls.md)
- [Hosting a Windows Forms Control in WPF Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF) (Ejemplo de cómo hospedar un control de Windows Forms en WPF)
