---
title: 'Tutorial: Hospedar un control de Windows Forms en WPF mediante XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: b55a51a7ca16416b6963c57395da2f2a88a55648
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548589"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="c7c6e-102">Tutorial: Hospedar un control de Windows Forms en WPF mediante XAML</span><span class="sxs-lookup"><span data-stu-id="c7c6e-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="c7c6e-103"> proporciona numerosos controles con un conjunto de características enriquecidas.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-103"> provides many controls with a rich feature set.</span></span> <span data-ttu-id="c7c6e-104">Sin embargo, en ocasiones, puede usar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] a los controles de su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] páginas.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="c7c6e-105">Por ejemplo, puede tener una inversión sustancial en existente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles, o tal vez tenga un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control que proporciona la funcionalidad exclusiva.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="c7c6e-106">En este tutorial se muestra cómo hospedar un formulario Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> controlar en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] página utilizando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7c6e-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="c7c6e-107">Para obtener una lista de código completa de las tareas mostradas en este tutorial, vea [hospedar un Control de formularios Windows Forms en WPF by Using XAML Sample](http://go.microsoft.com/fwlink/?LinkID=160000).</span><span class="sxs-lookup"><span data-stu-id="c7c6e-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](http://go.microsoft.com/fwlink/?LinkID=160000).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c7c6e-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c7c6e-108">Prerequisites</span></span>  
 <span data-ttu-id="c7c6e-109">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="c7c6e-109">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="c7c6e-110">.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-110">.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="c7c6e-111">Hospedar el control de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c7c6e-111">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="c7c6e-112">Para hospedar el control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="c7c6e-112">To host the MaskedTextBox control</span></span>  
  
1.  <span data-ttu-id="c7c6e-113">Cree un proyecto de aplicación WPF denominado `HostingWfInWpfWithXaml`.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-113">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2.  <span data-ttu-id="c7c6e-114">Agregue referencias a los ensamblados siguientes.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-114">Add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="c7c6e-115">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="c7c6e-115">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="c7c6e-116">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="c7c6e-116">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="c7c6e-117">Abra MainWindow.xaml en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7c6e-117">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="c7c6e-118">En el <xref:System.Windows.Window> elemento, agregue la siguiente asignación de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-118">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="c7c6e-119">El `wf` asignación de espacio de nombres establece una referencia al ensamblado que contiene el control de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-119">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="c7c6e-120">En el <xref:System.Windows.Controls.Grid> elemento Agregar el código XAML siguiente.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-120">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="c7c6e-121">El <xref:System.Windows.Forms.MaskedTextBox> control se crea como un elemento secundario de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-121">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  <span data-ttu-id="c7c6e-122">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c7c6e-122">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7c6e-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7c6e-123">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="c7c6e-124">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="c7c6e-124">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="c7c6e-125">Tutorial: Hospedar un control de Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="c7c6e-125">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [<span data-ttu-id="c7c6e-126">Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="c7c6e-126">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="c7c6e-127">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c7c6e-127">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="c7c6e-128">Controles de Windows Forms y controles equivalentes de WPF</span><span class="sxs-lookup"><span data-stu-id="c7c6e-128">Windows Forms Controls and Equivalent WPF Controls</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)  
 [<span data-ttu-id="c7c6e-129">Hospedar un Control de Windows Forms en WPF mediante XAML de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7c6e-129">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160000)
