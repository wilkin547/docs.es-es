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
ms.openlocfilehash: f7e925529f1bf194664c4f776bcc0322314f8857
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744907"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="89a04-102">Tutorial: Hospedar un control de Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="89a04-102">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="89a04-103">proporciona numerosos controles con un conjunto de características enriquecidas.</span><span class="sxs-lookup"><span data-stu-id="89a04-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="89a04-104">Sin embargo, a veces es posible que desee usar controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en las páginas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89a04-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="89a04-105">Por ejemplo, puede tener una inversión sustancial en los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] existentes o puede tener un control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] que proporcione una funcionalidad única.</span><span class="sxs-lookup"><span data-stu-id="89a04-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>

<span data-ttu-id="89a04-106">En este tutorial se muestra cómo hospedar un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> en una página de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante el uso de código.</span><span class="sxs-lookup"><span data-stu-id="89a04-106">This walkthrough shows you how to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>

<span data-ttu-id="89a04-107">Para obtener una lista de código completa de las tareas que se muestran en este tutorial, vea [hospedar un control de Windows Forms en el ejemplo de WPF](https://go.microsoft.com/fwlink/?LinkID=160057).</span><span class="sxs-lookup"><span data-stu-id="89a04-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="89a04-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="89a04-108">Prerequisites</span></span>

<span data-ttu-id="89a04-109">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="89a04-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="89a04-110">Hospedar el control de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="89a04-110">Hosting the Windows Forms Control</span></span>

### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="89a04-111">Para hospedar el control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="89a04-111">To host the MaskedTextBox control</span></span>

1. <span data-ttu-id="89a04-112">Cree un proyecto de aplicación de WPF denominado `HostingWfInWpf`.</span><span class="sxs-lookup"><span data-stu-id="89a04-112">Create a WPF Application project named `HostingWfInWpf`.</span></span>

2. <span data-ttu-id="89a04-113">Agregue referencias a los ensamblados siguientes.</span><span class="sxs-lookup"><span data-stu-id="89a04-113">Add references to the following assemblies.</span></span>

    - <span data-ttu-id="89a04-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="89a04-114">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="89a04-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="89a04-115">System.Windows.Forms</span></span>

3. <span data-ttu-id="89a04-116">Abra MainWindow. XAML en el diseñador de WPF.</span><span class="sxs-lookup"><span data-stu-id="89a04-116">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="89a04-117">Asigne al elemento <xref:System.Windows.Controls.Grid> el nombre `grid1`.</span><span class="sxs-lookup"><span data-stu-id="89a04-117">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. <span data-ttu-id="89a04-118">En Vista de diseño o en la vista XAML, seleccione el elemento <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="89a04-118">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="89a04-119">En el ventana Propiedades, haga clic en la pestaña **eventos** .</span><span class="sxs-lookup"><span data-stu-id="89a04-119">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="89a04-120">Haga doble clic en el evento <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="89a04-120">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="89a04-121">Inserte el código siguiente para controlar el evento <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="89a04-121">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. <span data-ttu-id="89a04-122">En la parte superior del archivo, agregue la siguiente `Imports` o `using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="89a04-122">At the top of the file, add the following `Imports` or `using` statement.</span></span>

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. <span data-ttu-id="89a04-123">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="89a04-123">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="89a04-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="89a04-124">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="89a04-125">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="89a04-125">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="89a04-126">Tutorial: Hospedar un control de formularios Windows Forms en WPF mediante XAML</span><span class="sxs-lookup"><span data-stu-id="89a04-126">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [<span data-ttu-id="89a04-127">Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="89a04-127">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="89a04-128">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="89a04-128">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="89a04-129">Controles de Windows Forms y controles equivalentes de WPF</span><span class="sxs-lookup"><span data-stu-id="89a04-129">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- <span data-ttu-id="89a04-130">[Hosting a Windows Forms Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057) (Ejemplo de cómo hospedar un control de Windows Forms en WPF)</span><span class="sxs-lookup"><span data-stu-id="89a04-130">[Hosting a Windows Forms Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057)</span></span>
