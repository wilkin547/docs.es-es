---
title: 'Cómo: Habilitar estilos visuales en una aplicación híbrida'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: dd52313e9100f9c6a1141b53ccc5a23a4b54410a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789919"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a><span data-ttu-id="ae2e9-102">Cómo: Habilitar estilos visuales en una aplicación híbrida</span><span class="sxs-lookup"><span data-stu-id="ae2e9-102">How to: Enable Visual Styles in a Hybrid Application</span></span>
<span data-ttu-id="ae2e9-103">En este tema se muestra cómo habilitar los estilos visuales en un control de Windows Forms hospedado en una aplicación basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae2e9-103">This topic shows how to enable visual styles on a Windows Forms control hosted in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
 <span data-ttu-id="ae2e9-104">Si la aplicación llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>, la mayoría de los controles Windows Forms usarán automáticamente los estilos visuales.</span><span class="sxs-lookup"><span data-stu-id="ae2e9-104">If your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method, most of your Windows Forms controls will automatically use visual styles.</span></span> <span data-ttu-id="ae2e9-105">Para obtener más información, consulte [Representar controles con estilos visuales](../../winforms/controls/rendering-controls-with-visual-styles.md).</span><span class="sxs-lookup"><span data-stu-id="ae2e9-105">For more information, see [Rendering Controls with Visual Styles](../../winforms/controls/rendering-controls-with-visual-styles.md).</span></span>  
  
 <span data-ttu-id="ae2e9-106">Para obtener una lista de código completa de las tareas que se ilustran en este tema, vea el [ejemplo de cómo habilitar estilos visuales en una aplicación híbrida](https://go.microsoft.com/fwlink/?LinkID=159986).</span><span class="sxs-lookup"><span data-stu-id="ae2e9-106">For a complete code listing of the tasks illustrated in this topic, see [Enabling Visual Styles in a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=159986).</span></span>  
  
## <a name="enabling-windows-forms-visual-styles"></a><span data-ttu-id="ae2e9-107">Habilitar estilos visuales de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae2e9-107">Enabling Windows Forms Visual Styles</span></span>  
  
#### <a name="to-enable-windows-forms-visual-styles"></a><span data-ttu-id="ae2e9-108">Para habilitar estilos visuales de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae2e9-108">To enable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="ae2e9-109">Cree un proyecto de aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] denominado `HostingWfWithVisualStyles`.</span><span class="sxs-lookup"><span data-stu-id="ae2e9-109">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Application project named `HostingWfWithVisualStyles`.</span></span>  
  
2. <span data-ttu-id="ae2e9-110">En el Explorador de soluciones, agregue referencias a los ensamblados siguientes.</span><span class="sxs-lookup"><span data-stu-id="ae2e9-110">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="ae2e9-111">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="ae2e9-111">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="ae2e9-112">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="ae2e9-112">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="ae2e9-113">En el cuadro de herramientas, haga doble clic en el icono de <xref:System.Windows.Controls.Grid> para colocar un elemento de <xref:System.Windows.Controls.Grid> en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="ae2e9-113">In the Toolbox, double-click the <xref:System.Windows.Controls.Grid> icon to place a <xref:System.Windows.Controls.Grid> element on the design surface.</span></span>  
  
4. <span data-ttu-id="ae2e9-114">En el ventana Propiedades, establezca los valores de las propiedades <xref:System.Windows.FrameworkElement.Height%2A> y <xref:System.Windows.FrameworkElement.Width%2A> en **auto**.</span><span class="sxs-lookup"><span data-stu-id="ae2e9-114">In the Properties window, set the values of the <xref:System.Windows.FrameworkElement.Height%2A> and <xref:System.Windows.FrameworkElement.Width%2A> properties to **Auto**.</span></span>  
  
5. <span data-ttu-id="ae2e9-115">En Vista de diseño o en la vista XAML, seleccione el <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="ae2e9-115">In Design view or XAML view, select the <xref:System.Windows.Window>.</span></span>  
  
6. <span data-ttu-id="ae2e9-116">En el ventana Propiedades, haga clic en la pestaña **eventos** .</span><span class="sxs-lookup"><span data-stu-id="ae2e9-116">In the Properties window, click the **Events** tab.</span></span>  
  
7. <span data-ttu-id="ae2e9-117">Haga doble clic en el evento <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="ae2e9-117">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>
  
8. <span data-ttu-id="ae2e9-118">En MainWindow. Xaml. vb o MainWindow.xaml.cs, inserte el siguiente código para controlar el evento <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="ae2e9-118">In MainWindow.xaml.vb or MainWindow.xaml.cs, insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. <span data-ttu-id="ae2e9-119">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae2e9-119">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="ae2e9-120">El control Windows Forms se dibuja con estilos visuales.</span><span class="sxs-lookup"><span data-stu-id="ae2e9-120">The Windows Forms control is painted with visual styles.</span></span>  
  
## <a name="disabling-windows-forms-visual-styles"></a><span data-ttu-id="ae2e9-121">Deshabilitar estilos visuales de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae2e9-121">Disabling Windows Forms Visual Styles</span></span>  
 <span data-ttu-id="ae2e9-122">Para deshabilitar los estilos visuales, simplemente quite la llamada al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="ae2e9-122">To disable visual styles, simply remove the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
#### <a name="to-disable-windows-forms-visual-styles"></a><span data-ttu-id="ae2e9-123">Para deshabilitar estilos visuales de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae2e9-123">To disable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="ae2e9-124">Abra MainWindow.xaml.vb o MainWindow.xaml.cs en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="ae2e9-124">Open MainWindow.xaml.vb or MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2. <span data-ttu-id="ae2e9-125">Convoque como comentario la llamada al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="ae2e9-125">Comment out the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
3. <span data-ttu-id="ae2e9-126">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ae2e9-126">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="ae2e9-127">El control Windows Forms se pinta con el estilo predeterminado del sistema.</span><span class="sxs-lookup"><span data-stu-id="ae2e9-127">The Windows Forms control is painted with the default system style.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae2e9-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae2e9-128">See also</span></span>

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="ae2e9-129">Representar controles con estilos visuales</span><span class="sxs-lookup"><span data-stu-id="ae2e9-129">Rendering Controls with Visual Styles</span></span>](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [<span data-ttu-id="ae2e9-130">Tutorial: Hospedar un control de Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="ae2e9-130">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
