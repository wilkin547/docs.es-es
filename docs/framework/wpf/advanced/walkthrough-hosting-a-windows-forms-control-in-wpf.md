---
title: 'Tutorial: Hospedar un control de formularios Windows Forms en WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: af5a0d58e789e609a25aa828493a3b0722cc83e1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605474"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="3b2b7-102">Tutorial: Hospedar un control de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="3b2b7-102">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="3b2b7-103">proporciona numerosos controles con un conjunto de características enriquecidas.</span><span class="sxs-lookup"><span data-stu-id="3b2b7-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="3b2b7-104">Sin embargo, es posible que a veces desea utilizar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] a los controles de su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] páginas.</span><span class="sxs-lookup"><span data-stu-id="3b2b7-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="3b2b7-105">Por ejemplo, puede tener una inversión sustancial en existente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles, o bien puede tener un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control que ofrece una funcionalidad única.</span><span class="sxs-lookup"><span data-stu-id="3b2b7-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>

<span data-ttu-id="3b2b7-106">En este tutorial se muestra cómo hospedar un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] página mediante código.</span><span class="sxs-lookup"><span data-stu-id="3b2b7-106">This walkthrough shows you how to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>

<span data-ttu-id="3b2b7-107">Para obtener una lista de código completo de las tareas mostradas en este tutorial, vea [hospedar un Control de Windows Forms en WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057).</span><span class="sxs-lookup"><span data-stu-id="3b2b7-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3b2b7-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3b2b7-108">Prerequisites</span></span>

<span data-ttu-id="3b2b7-109">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="3b2b7-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="3b2b7-110">Hospedar el control de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3b2b7-110">Hosting the Windows Forms Control</span></span>

### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="3b2b7-111">Para hospedar el control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="3b2b7-111">To host the MaskedTextBox control</span></span>

1. <span data-ttu-id="3b2b7-112">Cree un proyecto de aplicación WPF denominado `HostingWfInWpf`.</span><span class="sxs-lookup"><span data-stu-id="3b2b7-112">Create a WPF Application project named `HostingWfInWpf`.</span></span>

2. <span data-ttu-id="3b2b7-113">Agregue referencias a los ensamblados siguientes.</span><span class="sxs-lookup"><span data-stu-id="3b2b7-113">Add references to the following assemblies.</span></span>

    - <span data-ttu-id="3b2b7-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="3b2b7-114">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="3b2b7-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="3b2b7-115">System.Windows.Forms</span></span>

3. <span data-ttu-id="3b2b7-116">Abra MainWindow.xaml en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b2b7-116">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

4. <span data-ttu-id="3b2b7-117">Nombre de la <xref:System.Windows.Controls.Grid> elemento `grid1`.</span><span class="sxs-lookup"><span data-stu-id="3b2b7-117">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. <span data-ttu-id="3b2b7-118">En la vista Diseño o la vista XAML, seleccione el <xref:System.Windows.Window> elemento.</span><span class="sxs-lookup"><span data-stu-id="3b2b7-118">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="3b2b7-119">En la ventana Propiedades, haga clic en el **eventos** ficha.</span><span class="sxs-lookup"><span data-stu-id="3b2b7-119">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="3b2b7-120">Haga doble clic en el <xref:System.Windows.FrameworkElement.Loaded> eventos.</span><span class="sxs-lookup"><span data-stu-id="3b2b7-120">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="3b2b7-121">Inserte el código siguiente para controlar el <xref:System.Windows.FrameworkElement.Loaded> eventos.</span><span class="sxs-lookup"><span data-stu-id="3b2b7-121">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. <span data-ttu-id="3b2b7-122">En la parte superior del archivo, agregue el siguiente `Imports` o `using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="3b2b7-122">At the top of the file, add the following `Imports` or `using` statement.</span></span>

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. <span data-ttu-id="3b2b7-123">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3b2b7-123">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b2b7-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b2b7-124">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="3b2b7-125">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3b2b7-125">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="3b2b7-126">Tutorial: Hospedar un Control de Windows Forms en WPF mediante XAML</span><span class="sxs-lookup"><span data-stu-id="3b2b7-126">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [<span data-ttu-id="3b2b7-127">Tutorial: Hospedar un Control compuesto de Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="3b2b7-127">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="3b2b7-128">Tutorial: Hospedar un Control compuesto de WPF en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3b2b7-128">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="3b2b7-129">Controles de Windows Forms y controles equivalentes de WPF</span><span class="sxs-lookup"><span data-stu-id="3b2b7-129">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- <span data-ttu-id="3b2b7-130">[Hosting a Windows Forms Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057) (Ejemplo de cómo hospedar un control de Windows Forms en WPF)</span><span class="sxs-lookup"><span data-stu-id="3b2b7-130">[Hosting a Windows Forms Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=160057)</span></span>
