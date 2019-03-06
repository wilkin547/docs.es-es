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
ms.openlocfilehash: 300fd8d6c6bc8a73257d71280bbb0b5565c275ec
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375563"
---
# <a name="treeview-styles-and-templates"></a>Estilos y plantillas de TreeView
En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.TreeView> control. Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para proporcionar el control una apariencia única. Para más información, consulte [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="treeview-parts"></a>Elementos de TreeView  
 El <xref:System.Windows.Controls.TreeView> control no tiene elementos con nombre.  
  
 Cuando creas un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.TreeView>, la plantilla podría contener un <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>. (El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento en el <xref:System.Windows.Controls.TreeView>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).  Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo de la <xref:System.Windows.Controls.ScrollViewer>, debe proporcionar el <xref:System.Windows.Controls.ItemsPresenter> el nombre, `ItemsPresenter`.  
  
## <a name="treeview-states"></a>Estados de vista de árbol  
 En la tabla siguiente se enumera los estados visuales para el <xref:System.Windows.Controls.TreeView> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Válido|ValidationStates|El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|  
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|  
  
## <a name="treeviewitem-parts"></a>Partes de TreeViewItem  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.TreeViewItem> control.  
  
|Parte|Tipo|Descripción|  
|----------|----------|-----------------|  
|PART_Header|<xref:System.Windows.FrameworkElement>|Un elemento visual que contiene ese encabezado de contenido de la <xref:System.Windows.Controls.TreeView> control.|  
  
## <a name="treeviewitem-states"></a>Estados de TreeViewItem  
 En la tabla siguiente se enumera los estados visuales para <xref:System.Windows.Controls.TreeViewItem> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|----------------------|---------------------------|-----------------|  
|Normal|CommonStates|El estado predeterminado.|  
|MouseOver|CommonStates|Se coloca el puntero del mouse sobre el <xref:System.Windows.Controls.TreeViewItem>.|  
|Deshabilitado|CommonStates|El <xref:System.Windows.Controls.TreeViewItem> está deshabilitado.|  
|Con foco|FocusStates|El <xref:System.Windows.Controls.TreeViewItem> tiene el foco.|  
|Sin foco|FocusStates|El <xref:System.Windows.Controls.TreeViewItem> no tiene el foco.|  
|Expandido|ExpansionStates|El <xref:System.Windows.Controls.TreeViewItem> control está expandido.|  
|Collapsed|ExpansionStates|El <xref:System.Windows.Controls.TreeViewItem> está contraído.|  
|HasItems|HasItemsStates|El <xref:System.Windows.Controls.TreeViewItem> tiene elementos.|  
|NoItems|HasItemsStates|El <xref:System.Windows.Controls.TreeViewItem> no tiene elementos.|  
|Seleccionado|SelectionStates|El <xref:System.Windows.Controls.TreeViewItem> está seleccionada.|  
|SelectedInactive|SelectionStates|El <xref:System.Windows.Controls.TreeViewItem> está seleccionada pero no está activo.|  
|No seleccionado|SelectionStates|El <xref:System.Windows.Controls.TreeViewItem> no está seleccionada.|  
|Válido|ValidationStates|El control utiliza el <xref:System.Windows.Controls.Validation> clase y el <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|  
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|  
  
## <a name="treeview-controltemplate-example"></a>Ejemplo de ControlTemplate de TreeView  
 El ejemplo siguiente muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.TreeView> control y sus tipos asociados.  
  
 [!code-xaml[ControlTemplateExamples#TreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/treeview.xaml#treeview)]  
  
 En el ejemplo anterior se usa uno o varios de los recursos siguientes.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Estilos y plantillas de controles](control-styles-and-templates.md)
- [Control Customization](control-customization.md) (Personalización de controles)
- [Aplicar estilos y plantillas](styling-and-templating.md)
- [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
