---
title: Controles de Windows Forms y controles equivalentes de WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
ms.openlocfilehash: acb8095b32364f1e22330f22df60085016bdc664
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2019
ms.locfileid: "66834039"
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a><span data-ttu-id="c1576-102">Controles de Windows Forms y controles equivalentes de WPF</span><span class="sxs-lookup"><span data-stu-id="c1576-102">Windows Forms Controls and Equivalent WPF Controls</span></span>
<span data-ttu-id="c1576-103">Muchos [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles tienen equivalentes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controles, pero algunos [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles no tienen equivalentes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1576-103">Many [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls, but some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have no equivalents in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="c1576-104">Este tema comparan los tipos de control proporcionados por las dos tecnologías.</span><span class="sxs-lookup"><span data-stu-id="c1576-104">This topic compares control types provided by the two technologies.</span></span>  
  
 <span data-ttu-id="c1576-105">Siempre puede utilizar la interoperación con host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles que no tienen equivalentes en su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-aplicaciones basadas en.</span><span class="sxs-lookup"><span data-stu-id="c1576-105">You can always use interoperation to host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls that do not have equivalents in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
 <span data-ttu-id="c1576-106">En la tabla siguiente se muestra qué [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles y componentes tienen un equivalente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlen la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="c1576-106">The following table shows which [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and components have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control functionality.</span></span>  
  
|<span data-ttu-id="c1576-107">control de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1576-107">Windows Forms control</span></span>|<span data-ttu-id="c1576-108">Controles equivalentes de WPF</span><span class="sxs-lookup"><span data-stu-id="c1576-108">WPF equivalent control</span></span>|<span data-ttu-id="c1576-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1576-109">Remarks</span></span>|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|<span data-ttu-id="c1576-110">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="c1576-110">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<span data-ttu-id="c1576-111"><xref:System.Windows.Controls.ListBox> con la composición.</span><span class="sxs-lookup"><span data-stu-id="c1576-111"><xref:System.Windows.Controls.ListBox> with composition.</span></span>||  
|<xref:System.Windows.Forms.ColorDialog>|<span data-ttu-id="c1576-112">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="c1576-112">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<span data-ttu-id="c1576-113"><xref:System.Windows.Controls.ComboBox> no admite Autocompletar.</span><span class="sxs-lookup"><span data-stu-id="c1576-113"><xref:System.Windows.Controls.ComboBox> does not support auto-complete.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<span data-ttu-id="c1576-114"><xref:System.Windows.Controls.TextBox> y dos <xref:System.Windows.Controls.Primitives.RepeatButton> controles.</span><span class="sxs-lookup"><span data-stu-id="c1576-114"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.ErrorProvider>|<span data-ttu-id="c1576-115">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="c1576-115">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<span data-ttu-id="c1576-116"><xref:System.Windows.Controls.WrapPanel> o <xref:System.Windows.Controls.StackPanel></span><span class="sxs-lookup"><span data-stu-id="c1576-116"><xref:System.Windows.Controls.WrapPanel> or <xref:System.Windows.Controls.StackPanel></span></span>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|<span data-ttu-id="c1576-117">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="c1576-117">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FontDialog>|<span data-ttu-id="c1576-118">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="c1576-118">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<span data-ttu-id="c1576-119"><xref:System.Windows.Window> no se admite ventanas secundarias.</span><span class="sxs-lookup"><span data-stu-id="c1576-119"><xref:System.Windows.Window> does not support child windows.</span></span>|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|<span data-ttu-id="c1576-120">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="c1576-120">No equivalent control.</span></span>|<span data-ttu-id="c1576-121">No hay ayuda F1.</span><span class="sxs-lookup"><span data-stu-id="c1576-121">No F1 Help.</span></span> <span data-ttu-id="c1576-122">"¿Qué es esto" Ayuda se reemplaza por información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="c1576-122">"What's This" Help is replaced by ToolTips.</span></span>|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="c1576-123">El desplazamiento está integrado en los controles del contenedor.</span><span class="sxs-lookup"><span data-stu-id="c1576-123">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.ImageList>|<span data-ttu-id="c1576-124">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="c1576-124">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|<span data-ttu-id="c1576-125">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="c1576-125">No equivalent control.</span></span>|<span data-ttu-id="c1576-126">Puede usar el <xref:System.Windows.Documents.Hyperlink> clase hospedar hipervínculos dentro del contenido dinámico.</span><span class="sxs-lookup"><span data-stu-id="c1576-126">You can use the <xref:System.Windows.Documents.Hyperlink> class to host hyperlinks within flow content.</span></span>|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|<span data-ttu-id="c1576-127">El <xref:System.Windows.Controls.ListView> control proporciona una vista de detalles de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="c1576-127">The <xref:System.Windows.Controls.ListView> control provides a read-only details view.</span></span>|  
|<xref:System.Windows.Forms.MaskedTextBox>|<span data-ttu-id="c1576-128">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="c1576-128">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|<span data-ttu-id="c1576-129"><xref:System.Windows.Controls.Menu> estilos de control pueden aproximar el comportamiento y apariencia de la <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> clase.</span><span class="sxs-lookup"><span data-stu-id="c1576-129"><xref:System.Windows.Controls.Menu> control styling can approximate the behavior and appearance of the <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> class.</span></span>|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|<span data-ttu-id="c1576-130">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="c1576-130">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.NumericUpDown>|<span data-ttu-id="c1576-131"><xref:System.Windows.Controls.TextBox> y dos <xref:System.Windows.Controls.Primitives.RepeatButton> controles.</span><span class="sxs-lookup"><span data-stu-id="c1576-131"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|<span data-ttu-id="c1576-132">El <xref:Microsoft.Win32.OpenFileDialog> clase es un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenedor en torno a la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span><span class="sxs-lookup"><span data-stu-id="c1576-132">The <xref:Microsoft.Win32.OpenFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.PageSetupDialog>|<span data-ttu-id="c1576-133">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="c1576-133">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|<span data-ttu-id="c1576-134">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="c1576-134">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|<span data-ttu-id="c1576-135">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="c1576-135">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|<span data-ttu-id="c1576-136">No hay control equivalente.</span><span class="sxs-lookup"><span data-stu-id="c1576-136">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|<span data-ttu-id="c1576-137">El <xref:Microsoft.Win32.SaveFileDialog> clase es un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenedor en torno a la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span><span class="sxs-lookup"><span data-stu-id="c1576-137">The <xref:Microsoft.Win32.SaveFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="c1576-138"><xref:System.Windows.Controls.ToolBar> con la composición.</span><span class="sxs-lookup"><span data-stu-id="c1576-138"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="c1576-139"><xref:System.Windows.Controls.ToolBar> con la composición.</span><span class="sxs-lookup"><span data-stu-id="c1576-139"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<span data-ttu-id="c1576-140"><xref:System.Windows.Controls.ToolBar> con la composición.</span><span class="sxs-lookup"><span data-stu-id="c1576-140"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripPanel>|<span data-ttu-id="c1576-141"><xref:System.Windows.Controls.ToolBar> con la composición.</span><span class="sxs-lookup"><span data-stu-id="c1576-141"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="c1576-142">El desplazamiento está integrado en los controles del contenedor.</span><span class="sxs-lookup"><span data-stu-id="c1576-142">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.WebBrowser>|<span data-ttu-id="c1576-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c1576-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span></span>|<span data-ttu-id="c1576-144">El <xref:System.Windows.Controls.Frame> control puede hospedar páginas HTML.</span><span class="sxs-lookup"><span data-stu-id="c1576-144">The <xref:System.Windows.Controls.Frame> control can host HTML pages.</span></span><br /><br /> <span data-ttu-id="c1576-145">A partir de .NET Framework 3.5 SP1, el <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> control puede hospedar páginas HTML y también realiza una copia de la <xref:System.Windows.Controls.Frame> control.</span><span class="sxs-lookup"><span data-stu-id="c1576-145">Starting in the .NET Framework 3.5 SP1, the <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> control can host HTML pages and also backs the <xref:System.Windows.Controls.Frame> control.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1576-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1576-146">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- <span data-ttu-id="c1576-147">[WPF Designer para Windows Forms a los desarrolladores](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c1576-147">[WPF Designer for Windows Forms Developers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))</span></span>
- [<span data-ttu-id="c1576-148">Tutorial: Hospedar un Control de Windows Forms en WPF</span><span class="sxs-lookup"><span data-stu-id="c1576-148">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="c1576-149">Tutorial: Hospedar un Control compuesto de WPF en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1576-149">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="c1576-150">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="c1576-150">Migration and Interoperability</span></span>](migration-and-interoperability.md)
