---
title: Controles de Windows Forms y controles equivalentes de WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
ms.openlocfilehash: 7f531b60d8b31181688f3d0a6753b234ffc6c7dd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735209"
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a>Controles de Windows Forms y controles equivalentes de WPF
Muchos controles [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tienen controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] equivalentes, pero algunos controles [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no tienen ningún equivalente en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. En este tema se comparan los tipos de control proporcionados por las dos tecnologías.  
  
 Siempre puede usar la interoperación para hospedar [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles que no tienen equivalentes en las aplicaciones basadas en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 En la tabla siguiente se muestra qué controles y componentes de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tienen una funcionalidad de control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] equivalente.  
  
|control de Windows Forms|Control equivalente de WPF|Notas|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|Control no equivalente.||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<xref:System.Windows.Controls.ListBox> con composición.||  
|<xref:System.Windows.Forms.ColorDialog>|Control no equivalente.||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<xref:System.Windows.Controls.ComboBox> no admite la función de autocompletar.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<xref:System.Windows.Controls.TextBox> y dos controles <xref:System.Windows.Controls.Primitives.RepeatButton>.||  
|<xref:System.Windows.Forms.ErrorProvider>|Control no equivalente.||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<xref:System.Windows.Controls.WrapPanel> o <xref:System.Windows.Controls.StackPanel>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|Control no equivalente.||  
|<xref:System.Windows.Forms.FontDialog>|Control no equivalente.||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<xref:System.Windows.Window> no admite ventanas secundarias.|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|Control no equivalente.|No hay ayuda F1. La ayuda "Qué es esto" se reemplaza por la información sobre herramientas.|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|El desplazamiento está integrado en los controles de contenedor.|  
|<xref:System.Windows.Forms.ImageList>|Control no equivalente.||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|Control no equivalente.|Puede usar la clase <xref:System.Windows.Documents.Hyperlink> para hospedar hipervínculos dentro del contenido dinámico.|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|El control <xref:System.Windows.Controls.ListView> proporciona una vista de detalles de solo lectura.|  
|<xref:System.Windows.Forms.MaskedTextBox>|Control no equivalente.||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|<xref:System.Windows.Controls.Menu> el estilo de los controles puede aproximarse al comportamiento y la apariencia de la clase <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType>.|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|Control no equivalente.||  
|<xref:System.Windows.Forms.NumericUpDown>|<xref:System.Windows.Controls.TextBox> y dos controles <xref:System.Windows.Controls.Primitives.RepeatButton>.||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|La clase <xref:Microsoft.Win32.OpenFileDialog> es un contenedor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] alrededor del control Win32.|  
|<xref:System.Windows.Forms.PageSetupDialog>|Control no equivalente.||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|Control no equivalente.||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|Control no equivalente.||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|Control no equivalente.||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|La clase <xref:Microsoft.Win32.SaveFileDialog> es un contenedor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] alrededor del control Win32.|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<xref:System.Windows.Controls.ToolBar> con composición.||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<xref:System.Windows.Controls.ToolBar> con composición.||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<xref:System.Windows.Controls.ToolBar> con composición.||  
|<xref:System.Windows.Forms.ToolStripPanel>|<xref:System.Windows.Controls.ToolBar> con composición.||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|El desplazamiento está integrado en los controles de contenedor.|  
|<xref:System.Windows.Forms.WebBrowser>|<xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType>|El control <xref:System.Windows.Controls.Frame> puede hospedar páginas HTML.<br /><br /> A partir del .NET Framework 3,5 SP1, el <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> control puede hospedar páginas HTML y también hace una copia de seguridad del control <xref:System.Windows.Controls.Frame>.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [WPF Designer para Windows Forms desarrolladores](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))
- [Tutorial: Hospedar un control de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Migración e interoperabilidad](migration-and-interoperability.md)
