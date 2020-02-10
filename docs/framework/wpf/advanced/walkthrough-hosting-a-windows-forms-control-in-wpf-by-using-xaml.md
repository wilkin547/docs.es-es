---
title: Hospedar un control de Windows Forms en WPF mediante XAML
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 99c077801a26043e17e0d51ecc0a97b9608784c0
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095065"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="e5680-102">Tutorial: Hospedar un control de Windows Forms en WPF mediante XAML</span><span class="sxs-lookup"><span data-stu-id="e5680-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="e5680-103">proporciona numerosos controles con un conjunto de características enriquecidas.</span><span class="sxs-lookup"><span data-stu-id="e5680-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="e5680-104">Sin embargo, a veces es posible que desee usar controles de Windows Forms en las páginas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5680-104">However, you may sometimes want to use Windows Forms controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="e5680-105">Por ejemplo, puede tener una inversión sustancial en los controles de Windows Forms existentes o puede tener un control Windows Forms que proporcione una funcionalidad única.</span><span class="sxs-lookup"><span data-stu-id="e5680-105">For example, you may have a substantial investment in existing Windows Forms controls, or you may have a Windows Forms control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="e5680-106">En este tutorial se muestra cómo hospedar un control de Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> en una página de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5680-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="e5680-107">Para obtener una lista de código completa de las tareas que se muestran en este tutorial, vea [hospedar un control de Windows Forms en WPF mediante el ejemplo de XAML](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span><span class="sxs-lookup"><span data-stu-id="e5680-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="e5680-108">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="e5680-108">Prerequisites</span></span>  

<span data-ttu-id="e5680-109">Necesita Visual Studio para completar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="e5680-109">You need Visual Studio to complete this walkthrough.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="e5680-110">Hospedar el control de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5680-110">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="e5680-111">Para hospedar el control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="e5680-111">To host the MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="e5680-112">Cree un proyecto de aplicación de WPF denominado `HostingWfInWpfWithXaml`.</span><span class="sxs-lookup"><span data-stu-id="e5680-112">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2. <span data-ttu-id="e5680-113">Agregue referencias a los ensamblados siguientes.</span><span class="sxs-lookup"><span data-stu-id="e5680-113">Add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="e5680-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="e5680-114">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="e5680-115">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="e5680-115">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="e5680-116">Abra MainWindow. XAML en el diseñador de WPF.</span><span class="sxs-lookup"><span data-stu-id="e5680-116">Open MainWindow.xaml in the WPF Designer.</span></span>  
  
4. <span data-ttu-id="e5680-117">En el elemento <xref:System.Windows.Window>, agregue la siguiente asignación de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e5680-117">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="e5680-118">La asignación del espacio de nombres `wf` establece una referencia al ensamblado que contiene el control Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e5680-118">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <span data-ttu-id="e5680-119">En el elemento <xref:System.Windows.Controls.Grid>, agregue el siguiente código XAML.</span><span class="sxs-lookup"><span data-stu-id="e5680-119">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="e5680-120">El control <xref:System.Windows.Forms.MaskedTextBox> se crea como un elemento secundario del control <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="e5680-120">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. <span data-ttu-id="e5680-121">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e5680-121">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5680-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5680-122">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="e5680-123">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e5680-123">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="e5680-124">Tutorial: Hospedar un control de Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="e5680-124">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="e5680-125">Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="e5680-125">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="e5680-126">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5680-126">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="e5680-127">Controles de Windows Forms y controles equivalentes de WPF</span><span class="sxs-lookup"><span data-stu-id="e5680-127">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="e5680-128">Hospedar un control de Windows Forms en WPF mediante el ejemplo de XAML</span><span class="sxs-lookup"><span data-stu-id="e5680-128">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml)
