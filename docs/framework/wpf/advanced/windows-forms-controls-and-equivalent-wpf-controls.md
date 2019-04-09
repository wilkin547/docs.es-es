---
title: Controles de Windows Forms y controles equivalentes de WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
ms.openlocfilehash: abfcb9f5398a6a8d264985543df585bea93a0446
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075280"
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a><span data-ttu-id="423fe-102">Controles de Windows Forms y controles equivalentes de WPF</span><span class="sxs-lookup"><span data-stu-id="423fe-102">Windows Forms Controls and Equivalent WPF Controls</span></span>
<span data-ttu-id="423fe-103">Muchos [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles tienen equivalentes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controles, pero algunos [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles no tienen equivalentes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="423fe-103">Many [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls, but some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have no equivalents in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="423fe-104">Este tema comparan los tipos de control proporcionados por las dos tecnologías.</span><span class="sxs-lookup"><span data-stu-id="423fe-104">This topic compares control types provided by the two technologies.</span></span>  
  
 <span data-ttu-id="423fe-105">Siempre puede utilizar la interoperación con host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles que no tienen equivalentes en su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-aplicaciones basadas en.</span><span class="sxs-lookup"><span data-stu-id="423fe-105">You can always use interoperation to host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls that do not have equivalents in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
 <span data-ttu-id="423fe-106">En la tabla siguiente se muestra qué [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles y componentes tienen un equivalente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlen la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="423fe-106">The following table shows which [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and components have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control functionality.</span></span>  
  
|<span data-ttu-id="423fe-107">control de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="423fe-107">Windows Forms control</span></span>|<span data-ttu-id="423fe-108">Controles equivalentes de WPF</span><span class="sxs-lookup"><span data-stu-id="423fe-108">WPF equivalent control</span></span>|<span data-ttu-id="423fe-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="423fe-109">Remarks</span></span>|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|<span data-ttu-id="423fe-110">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="423fe-110">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<xref:System.Windows.Controls.ListBox> <span data-ttu-id="423fe-111">con la composición.</span><span class="sxs-lookup"><span data-stu-id="423fe-111">with composition.</span></span>||  
|<xref:System.Windows.Forms.ColorDialog>|<span data-ttu-id="423fe-112">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="423fe-112">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<xref:System.Windows.Controls.ComboBox> <span data-ttu-id="423fe-113">no admite Autocompletar.</span><span class="sxs-lookup"><span data-stu-id="423fe-113">does not support auto-complete.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<xref:System.Windows.Controls.TextBox> <span data-ttu-id="423fe-114">y dos <xref:System.Windows.Controls.Primitives.RepeatButton> controles.</span><span class="sxs-lookup"><span data-stu-id="423fe-114">and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.ErrorProvider>|<span data-ttu-id="423fe-115">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="423fe-115">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<xref:System.Windows.Controls.WrapPanel> <span data-ttu-id="423fe-116">o</span><span class="sxs-lookup"><span data-stu-id="423fe-116">or</span></span> <xref:System.Windows.Controls.StackPanel>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|<span data-ttu-id="423fe-117">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="423fe-117">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FontDialog>|<span data-ttu-id="423fe-118">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="423fe-118">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<xref:System.Windows.Window> <span data-ttu-id="423fe-119">no se admite ventanas secundarias.</span><span class="sxs-lookup"><span data-stu-id="423fe-119">does not support child windows.</span></span>|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|<span data-ttu-id="423fe-120">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="423fe-120">No equivalent control.</span></span>|<span data-ttu-id="423fe-121">No hay ayuda F1.</span><span class="sxs-lookup"><span data-stu-id="423fe-121">No F1 Help.</span></span> <span data-ttu-id="423fe-122">"¿Qué es esto" Ayuda se reemplaza por información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="423fe-122">"What's This" Help is replaced by ToolTips.</span></span>|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="423fe-123">El desplazamiento está integrado en los controles del contenedor.</span><span class="sxs-lookup"><span data-stu-id="423fe-123">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.ImageList>|<span data-ttu-id="423fe-124">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="423fe-124">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|<span data-ttu-id="423fe-125">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="423fe-125">No equivalent control.</span></span>|<span data-ttu-id="423fe-126">Puede usar el <xref:System.Windows.Documents.Hyperlink> clase hospedar hipervínculos dentro del contenido dinámico.</span><span class="sxs-lookup"><span data-stu-id="423fe-126">You can use the <xref:System.Windows.Documents.Hyperlink> class to host hyperlinks within flow content.</span></span>|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|<span data-ttu-id="423fe-127">El <xref:System.Windows.Controls.ListView> control proporciona una vista de detalles de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="423fe-127">The <xref:System.Windows.Controls.ListView> control provides a read-only details view.</span></span>|  
|<xref:System.Windows.Forms.MaskedTextBox>|<span data-ttu-id="423fe-128">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="423fe-128">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|<xref:System.Windows.Controls.Menu> <span data-ttu-id="423fe-129">estilos de control pueden aproximar el comportamiento y apariencia de la <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="423fe-129">control styling can approximate the behavior and appearance of the <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> class.</span></span>|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|<span data-ttu-id="423fe-130">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="423fe-130">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.NumericUpDown>|<xref:System.Windows.Controls.TextBox> <span data-ttu-id="423fe-131">y dos <xref:System.Windows.Controls.Primitives.RepeatButton> controles.</span><span class="sxs-lookup"><span data-stu-id="423fe-131">and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|<span data-ttu-id="423fe-132">El <xref:Microsoft.Win32.OpenFileDialog> clase es un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenedor en torno a la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span><span class="sxs-lookup"><span data-stu-id="423fe-132">The <xref:Microsoft.Win32.OpenFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.PageSetupDialog>|<span data-ttu-id="423fe-133">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="423fe-133">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|<span data-ttu-id="423fe-134">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="423fe-134">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|<span data-ttu-id="423fe-135">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="423fe-135">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|<span data-ttu-id="423fe-136">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="423fe-136">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|<span data-ttu-id="423fe-137">El <xref:Microsoft.Win32.SaveFileDialog> clase es un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenedor en torno a la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span><span class="sxs-lookup"><span data-stu-id="423fe-137">The <xref:Microsoft.Win32.SaveFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<xref:System.Windows.Controls.ToolBar> <span data-ttu-id="423fe-138">con la composición.</span><span class="sxs-lookup"><span data-stu-id="423fe-138">with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<xref:System.Windows.Controls.ToolBar> <span data-ttu-id="423fe-139">con la composición.</span><span class="sxs-lookup"><span data-stu-id="423fe-139">with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<xref:System.Windows.Controls.ToolBar> <span data-ttu-id="423fe-140">con la composición.</span><span class="sxs-lookup"><span data-stu-id="423fe-140">with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripPanel>|<xref:System.Windows.Controls.ToolBar> <span data-ttu-id="423fe-141">con la composición.</span><span class="sxs-lookup"><span data-stu-id="423fe-141">with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="423fe-142">El desplazamiento está integrado en los controles del contenedor.</span><span class="sxs-lookup"><span data-stu-id="423fe-142">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.WebBrowser>|<xref:System.Windows.Controls.Frame><span data-ttu-id="423fe-143">,</span><span class="sxs-lookup"><span data-stu-id="423fe-143">,</span></span> <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType>|<span data-ttu-id="423fe-144">El <xref:System.Windows.Controls.Frame> control puede hospedar páginas HTML.</span><span class="sxs-lookup"><span data-stu-id="423fe-144">The <xref:System.Windows.Controls.Frame> control can host HTML pages.</span></span><br /><br /> <span data-ttu-id="423fe-145">A partir de la [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> control puede hospedar páginas HTML y también realiza una copia de la <xref:System.Windows.Controls.Frame> control.</span><span class="sxs-lookup"><span data-stu-id="423fe-145">Starting in the [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], the <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> control can host HTML pages and also backs the <xref:System.Windows.Controls.Frame> control.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="423fe-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="423fe-146">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="423fe-147">WPF Designer para Windows Forms a los desarrolladores</span><span class="sxs-lookup"><span data-stu-id="423fe-147">WPF Designer for Windows Forms Developers</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))
- [<span data-ttu-id="423fe-148">Tutorial: Hospedar un control de formularios Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="423fe-148">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="423fe-149">Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="423fe-149">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="423fe-150">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="423fe-150">Migration and Interoperability</span></span>](migration-and-interoperability.md)
