---
title: 'Cómo: Copiar y pegar un control ElementHost en tiempo de diseño'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: 43ebe50497df97511925bd2e413ab5b5988b7f57
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45624793"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="130d0-102">Cómo: Copiar y pegar un control ElementHost en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="130d0-102">How to: Copy and Paste an ElementHost Control at Design Time</span></span>
<span data-ttu-id="130d0-103">Este procedimiento muestra cómo copiar un control de Windows Presentation Foundation (WPF) en un formulario de Windows.</span><span class="sxs-lookup"><span data-stu-id="130d0-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="130d0-104">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="130d0-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="130d0-105">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="130d0-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="130d0-106">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="130d0-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="130d0-107">Para copiar y pegar un control ElementHost en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="130d0-107">To copy and paste an ElementHost control at design time</span></span>  
  
1.  <span data-ttu-id="130d0-108">Agregue un nuevo WPF <xref:System.Windows.Controls.UserControl> a su proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="130d0-108">Add a new WPF <xref:System.Windows.Controls.UserControl> to your Windows Forms project.</span></span> <span data-ttu-id="130d0-109">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="130d0-109">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="130d0-110">Para obtener más información, consulte [Tutorial: crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="130d0-110">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="130d0-111">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> propiedades de `UserControl1` a `200`.</span><span class="sxs-lookup"><span data-stu-id="130d0-111">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to `200`.</span></span>  
  
3.  <span data-ttu-id="130d0-112">Establezca el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> en `Blue`.</span><span class="sxs-lookup"><span data-stu-id="130d0-112">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
4.  <span data-ttu-id="130d0-113">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="130d0-113">Build the project.</span></span>  
  
5.  <span data-ttu-id="130d0-114">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="130d0-114">Open `Form1` in the Windows Forms Designer.</span></span>  
  
6.  <span data-ttu-id="130d0-115">Desde el **cuadro de herramientas**, arrastre una instancia de `UserControl1` hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="130d0-115">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="130d0-116">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="130d0-116">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
7.  <span data-ttu-id="130d0-117">Con `elementHost1` seleccionado, presione CTRL+C para copiarlo en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="130d0-117">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
8.  <span data-ttu-id="130d0-118">Presione CTRL+V para pegar el control copiado en el formulario.</span><span class="sxs-lookup"><span data-stu-id="130d0-118">Press CTRL+V to paste the copied control onto the form.</span></span>  
  
     <span data-ttu-id="130d0-119">Un nuevo <xref:System.Windows.Forms.Integration.ElementHost> control denominado `elementHost2` se crea en el formulario.</span><span class="sxs-lookup"><span data-stu-id="130d0-119">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="130d0-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="130d0-120">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="130d0-121">Tutorial: Copiar y pegar un control ElementHost en formularios Windows Forms independientes</span><span class="sxs-lookup"><span data-stu-id="130d0-121">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 [<span data-ttu-id="130d0-122">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="130d0-122">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="130d0-123">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="130d0-123">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="130d0-124">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="130d0-124">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
