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
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a><span data-ttu-id="ed06c-102">Tutorial: Hospedar un control de Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="ed06c-102">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="ed06c-103">proporciona numerosos controles con un conjunto de características enriquecidas.</span><span class="sxs-lookup"><span data-stu-id="ed06c-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="ed06c-104">Sin embargo, a veces es posible que desee usar controles de Windows Forms en las páginas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed06c-104">However, you may sometimes want to use Windows Forms controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="ed06c-105">Por ejemplo, puede tener una inversión sustancial en los controles de Windows Forms existentes o puede tener un control Windows Forms que proporcione una funcionalidad única.</span><span class="sxs-lookup"><span data-stu-id="ed06c-105">For example, you may have a substantial investment in existing Windows Forms controls, or you may have a Windows Forms control that provides unique functionality.</span></span>

<span data-ttu-id="ed06c-106">En este tutorial se muestra cómo hospedar un control de Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> en una página de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante el uso de código.</span><span class="sxs-lookup"><span data-stu-id="ed06c-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using code.</span></span>

<span data-ttu-id="ed06c-107">Para obtener una lista de código completa de las tareas que se muestran en este tutorial, vea [hospedar un control de Windows Forms en el ejemplo de WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF).</span><span class="sxs-lookup"><span data-stu-id="ed06c-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ed06c-108">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="ed06c-108">Prerequisites</span></span>

<span data-ttu-id="ed06c-109">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="ed06c-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="ed06c-110">Hospedar el control de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ed06c-110">Hosting the Windows Forms Control</span></span>

### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="ed06c-111">Para hospedar el control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="ed06c-111">To host the MaskedTextBox control</span></span>

1. <span data-ttu-id="ed06c-112">Cree un proyecto de aplicación de WPF denominado `HostingWfInWpf`.</span><span class="sxs-lookup"><span data-stu-id="ed06c-112">Create a WPF Application project named `HostingWfInWpf`.</span></span>

2. <span data-ttu-id="ed06c-113">Agregue referencias a los ensamblados siguientes.</span><span class="sxs-lookup"><span data-stu-id="ed06c-113">Add references to the following assemblies.</span></span>

    - <span data-ttu-id="ed06c-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="ed06c-114">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="ed06c-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="ed06c-115">System.Windows.Forms</span></span>

3. <span data-ttu-id="ed06c-116">Abra MainWindow. XAML en el diseñador de WPF.</span><span class="sxs-lookup"><span data-stu-id="ed06c-116">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="ed06c-117">Asigne al elemento <xref:System.Windows.Controls.Grid> el nombre `grid1`.</span><span class="sxs-lookup"><span data-stu-id="ed06c-117">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>

     [!code-xaml[HostingWfInWPF#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5. <span data-ttu-id="ed06c-118">En Vista de diseño o en la vista XAML, seleccione el elemento <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="ed06c-118">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="ed06c-119">En el ventana Propiedades, haga clic en la pestaña **eventos** .</span><span class="sxs-lookup"><span data-stu-id="ed06c-119">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="ed06c-120">Haga doble clic en el evento <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="ed06c-120">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="ed06c-121">Inserte el código siguiente para controlar el evento <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="ed06c-121">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

     [!code-csharp[HostingWfInWPF#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. <span data-ttu-id="ed06c-122">En la parte superior del archivo, agregue la siguiente `Imports` o `using` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ed06c-122">At the top of the file, add the following `Imports` or `using` statement.</span></span>

     [!code-csharp[HostingWfInWPF#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. <span data-ttu-id="ed06c-123">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed06c-123">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed06c-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed06c-124">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="ed06c-125">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ed06c-125">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="ed06c-126">Tutorial: Hospedar un control de formularios Windows Forms en WPF mediante XAML</span><span class="sxs-lookup"><span data-stu-id="ed06c-126">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [<span data-ttu-id="ed06c-127">Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="ed06c-127">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="ed06c-128">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ed06c-128">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="ed06c-129">Controles de Windows Forms y controles equivalentes de WPF</span><span class="sxs-lookup"><span data-stu-id="ed06c-129">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- <span data-ttu-id="ed06c-130">[Hosting a Windows Forms Control in WPF Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF) (Ejemplo de cómo hospedar un control de Windows Forms en WPF)</span><span class="sxs-lookup"><span data-stu-id="ed06c-130">[Hosting a Windows Forms Control in WPF Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWPF)</span></span>
