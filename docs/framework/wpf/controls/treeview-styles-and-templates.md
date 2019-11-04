---
title: Estilos y plantillas de TreeView
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TreeView
- templates [WPF], TreeView
- parts [WPF], TreeView
- states [WPF], TreeView
- styles [WPF], TreeView
- TreeView [WPF], styles and templates
ms.assetid: a49adb77-0202-4caa-b94a-8bb110d7fa9a
ms.openlocfilehash: f6dbe54324a5ad5e2f85719d819c035abfd644b1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460188"
---
# <a name="treeview-styles-and-templates"></a>Estilos y plantillas de TreeView
En este tema se describen los estilos y las plantillas del control <xref:System.Windows.Controls.TreeView>. Puede modificar la <xref:System.Windows.Controls.ControlTemplate> predeterminada para dar al control una apariencia única. Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).  
  
## <a name="treeview-parts"></a>Elementos de TreeView  
 El control <xref:System.Windows.Controls.TreeView> no tiene ninguna parte con nombre.  
  
 Cuando se crea una <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.TreeView>, es posible que la plantilla contenga una <xref:System.Windows.Controls.ItemsPresenter> dentro de una <xref:System.Windows.Controls.ScrollViewer>. (El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento del <xref:System.Windows.Controls.TreeView>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).  Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo del <xref:System.Windows.Controls.ScrollViewer>, debe proporcionar al <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.  
  
## <a name="treeview-states"></a>Estados de TreeView  
 En la tabla siguiente se enumeran los Estados visuales del control <xref:System.Windows.Controls.TreeView>.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Válido|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.|  
  
## <a name="treeviewitem-parts"></a>Elementos TreeViewItem  
 En la tabla siguiente se enumeran las partes con nombre para el control <xref:System.Windows.Controls.TreeViewItem>.  
  
|Parte|Type|Descripción|  
|----------|----------|-----------------|  
|PART_Header|<xref:System.Windows.FrameworkElement>|Elemento visual que contiene el contenido del encabezado del control <xref:System.Windows.Controls.TreeView>.|  
  
## <a name="treeviewitem-states"></a>Estados de TreeViewItem  
 En la tabla siguiente se enumeran los Estados visuales de <xref:System.Windows.Controls.TreeViewItem> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|El puntero del mouse se coloca sobre el <xref:System.Windows.Controls.TreeViewItem>.|  
|Deshabilitado|CommonStates|La <xref:System.Windows.Controls.TreeViewItem> está deshabilitada.|  
|Con foco|FocusStates|El <xref:System.Windows.Controls.TreeViewItem> tiene el foco.|  
|Sin foco|FocusStates|El <xref:System.Windows.Controls.TreeViewItem> no tiene el foco.|  
|Expandido|ExpansionStates|Se expande el control <xref:System.Windows.Controls.TreeViewItem>.|  
|Collapsed|ExpansionStates|El control <xref:System.Windows.Controls.TreeViewItem> está contraído.|  
|HasItems|HasItemsStates|El <xref:System.Windows.Controls.TreeViewItem> tiene elementos.|  
|Noitems|HasItemsStates|El <xref:System.Windows.Controls.TreeViewItem> no tiene elementos.|  
|Seleccionado|SelectionStates|Se selecciona el <xref:System.Windows.Controls.TreeViewItem>.|  
|SelectedInactive|SelectionStates|El <xref:System.Windows.Controls.TreeViewItem> está seleccionado pero no activo.|  
|No seleccionado|SelectionStates|No se ha seleccionado el <xref:System.Windows.Controls.TreeViewItem>.|  
|Válido|ValidationStates|El control utiliza la clase <xref:System.Windows.Controls.Validation> y la propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `false`.|  
|InvalidFocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el foco.|  
|InvalidUnfocused|ValidationStates|La propiedad adjunta <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> es `true` tiene el control no tiene el foco.|  
  
## <a name="treeview-controltemplate-example"></a>Ejemplo de ControlTemplate de TreeView  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el control <xref:System.Windows.Controls.TreeView> y sus tipos asociados.  
  
 [!code-xaml[ControlTemplateExamples#TreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
 En el ejemplo anterior se usa uno o varios de los recursos siguientes.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Estilos y plantillas de controles](control-styles-and-templates.md)
- [Control Customization](control-customization.md) (Personalización de controles)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
