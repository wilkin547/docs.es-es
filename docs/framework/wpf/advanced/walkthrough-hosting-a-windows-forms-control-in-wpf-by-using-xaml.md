---
title: 'Tutorial: Hospedar un control de Windows Forms en WPF mediante XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 61a234a679d9937cb38a753a3d73f2ecc9ec891a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190374"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="5bb5a-102">Tutorial: Hospedar un control de Windows Forms en WPF mediante XAML</span><span class="sxs-lookup"><span data-stu-id="5bb5a-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="5bb5a-103">proporciona numerosos controles con un amplio conjunto de características.</span><span class="sxs-lookup"><span data-stu-id="5bb5a-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="5bb5a-104">Sin embargo, es posible que a veces desea utilizar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] a los controles de su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] páginas.</span><span class="sxs-lookup"><span data-stu-id="5bb5a-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="5bb5a-105">Por ejemplo, puede tener una inversión sustancial en existente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles, o bien puede tener un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control que ofrece una funcionalidad única.</span><span class="sxs-lookup"><span data-stu-id="5bb5a-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="5bb5a-106">En este tutorial se muestra cómo hospedar un formulario Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] página utilizando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bb5a-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="5bb5a-107">Para obtener una lista de código completo de las tareas mostradas en este tutorial, vea [hospedar un Control de Windows Forms en WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span><span class="sxs-lookup"><span data-stu-id="5bb5a-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="5bb5a-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5bb5a-108">Prerequisites</span></span>  

<span data-ttu-id="5bb5a-109">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="5bb5a-109">You need Visual Studio to complete this walkthrough.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="5bb5a-110">Hospedar el control de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5bb5a-110">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="5bb5a-111">Para hospedar el control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="5bb5a-111">To host the MaskedTextBox control</span></span>  
  
1.  <span data-ttu-id="5bb5a-112">Cree un proyecto de aplicación WPF denominado `HostingWfInWpfWithXaml`.</span><span class="sxs-lookup"><span data-stu-id="5bb5a-112">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2.  <span data-ttu-id="5bb5a-113">Agregue referencias a los ensamblados siguientes.</span><span class="sxs-lookup"><span data-stu-id="5bb5a-113">Add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="5bb5a-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="5bb5a-114">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="5bb5a-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="5bb5a-115">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="5bb5a-116">Abra MainWindow.xaml en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bb5a-116">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="5bb5a-117">En el <xref:System.Windows.Window> elemento, agregue la siguiente asignación de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5bb5a-117">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="5bb5a-118">El `wf` asignación del espacio de nombres establece una referencia al ensamblado que contiene el control Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5bb5a-118">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="5bb5a-119">En el <xref:System.Windows.Controls.Grid> elemento Agregar el XAML siguiente.</span><span class="sxs-lookup"><span data-stu-id="5bb5a-119">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="5bb5a-120">El <xref:System.Windows.Forms.MaskedTextBox> control se crea como un elemento secundario de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span><span class="sxs-lookup"><span data-stu-id="5bb5a-120">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  <span data-ttu-id="5bb5a-121">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5bb5a-121">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb5a-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bb5a-122">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="5bb5a-123">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5bb5a-123">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="5bb5a-124">Tutorial: Hospedar un control de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="5bb5a-124">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="5bb5a-125">Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="5bb5a-125">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="5bb5a-126">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5bb5a-126">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="5bb5a-127">Controles de Windows Forms y controles equivalentes de WPF</span><span class="sxs-lookup"><span data-stu-id="5bb5a-127">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="5bb5a-128">Hospedar un Control de Windows Forms en WPF mediante XAML de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bb5a-128">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160000)
