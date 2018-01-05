---
title: Estilos y plantillas de ToolBar
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], ToolBar
- styles [WPF], ToolBar
- ControlTemplate [WPF], ToolBar
- parts [WPF], ToolBar
- ToolBar [WPF], styles and templates
- templates [WPF], ToolBar
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d56858f3785a4d4d49a0781fbf4c19397a3bb375
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="toolbar-styles-and-templates"></a>Estilos y plantillas de ToolBar
En este tema se describe los estilos y plantillas para el <xref:System.Windows.Controls.ToolBar> control. Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única. Para más información, consulte [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md) (Personalizar la apariencia de un control existente mediante la creación de una clase ControlTemplate).  
  
## <a name="toolbar-parts"></a>Partes de la barra de herramientas  
 En la tabla siguiente se enumera los elementos con nombre para el <xref:System.Windows.Controls.ToolBar> control.  
  
|Parte|Tipo|Descripción|  
|-|-|-|  
|PART_ToolBarPanel|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|El objeto que contiene los controles en el <xref:System.Windows.Controls.ToolBar>.|  
|PART_ToolBarOverflowPanel|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|El objeto que contiene los controles que se encuentran en el área de desbordamiento de la <xref:System.Windows.Controls.ToolBar>.|  
  
 Cuando se crea un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.ToolBar>, la plantilla podría contener una <xref:System.Windows.Controls.ItemsPresenter> dentro de un <xref:System.Windows.Controls.ScrollViewer>. (El <xref:System.Windows.Controls.ItemsPresenter> muestra cada elemento de la <xref:System.Windows.Controls.ToolBar>; el <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento en el control).  Si el <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo de la <xref:System.Windows.Controls.ScrollViewer>, debe asignar a la <xref:System.Windows.Controls.ItemsPresenter> el nombre `ItemsPresenter`.  
  
## <a name="toolbar-states"></a>Estados de la barra de herramientas  
 La tabla siguiente enumera los estados visuales para el <xref:System.Windows.Controls.ToolBar> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Válido|ValidationStates|El control usa la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false`.|  
|InvalidFocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control tiene el foco.|  
|InvalidUnfocused|ValidationStates|El <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `true` tiene el control no tiene el foco.|  
  
## <a name="toolbar-controltemplate-example"></a>Ejemplo de ControlTemplate de barra de herramientas  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.ToolBar> control.  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 En el ejemplo anterior se usa uno o varios de los recursos siguientes.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Estilos y plantillas de controles](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Control Customization](../../../../docs/framework/wpf/controls/control-customization.md) (Personalización de controles)  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Personalización de la apariencia de un control existente mediante la creación de una clase ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
