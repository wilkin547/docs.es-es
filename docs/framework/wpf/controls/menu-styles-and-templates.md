---
title: Estilos y plantillas de menú
description: Obtenga información sobre los estilos y las plantillas del Windows Presentation Foundation el control de menú. Modifique el ControlTemplate para dar al control una apariencia única.
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
ms.openlocfilehash: 5187e4a479609686e39e043808931141ca52078c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164553"
---
# <a name="menu-styles-and-templates"></a>Estilos y plantillas de menú
En este tema se describen los estilos y las plantillas del <xref:System.Windows.Controls.Menu> control. Puede modificar el valor predeterminado <xref:System.Windows.Controls.ControlTemplate> para dar al control una apariencia única. Para obtener más información, vea [crear una plantilla para un control](../../../desktop-wpf/themes/how-to-create-apply-template.md).  
  
## <a name="menu-parts"></a>Elementos de menú  
 El <xref:System.Windows.Controls.Menu> control no tiene ninguna parte con nombre.  
  
 Cuando se crea un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.Menu> , la plantilla podría contener un <xref:System.Windows.Controls.ItemsPresenter> dentro de <xref:System.Windows.Controls.ScrollViewer> . ( <xref:System.Windows.Controls.ItemsPresenter> Muestra cada elemento en <xref:System.Windows.Controls.Menu> ; <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).  Si <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo de <xref:System.Windows.Controls.ScrollViewer> , debe proporcionar el <xref:System.Windows.Controls.ItemsPresenter> nombre, `ItemsPresenter` .  
  
## <a name="menu-states"></a>Estados de menú  
 En la tabla siguiente se enumeran los Estados visuales del <xref:System.Windows.Controls.Menu> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Válido|ValidationStates|El control utiliza la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false` .|  
|InvalidFocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta tiene `true` el foco.|  
|InvalidUnfocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta `true` tiene el control no tiene el foco.|  
  
## <a name="menuitem-parts"></a>Elementos MenuItem  
 En la tabla siguiente se enumeran las partes con nombre para el <xref:System.Windows.Controls.Menu> control.  
  
|Parte|Tipo|Description|  
|-|-|-|  
|PART_Popup|<xref:System.Windows.Controls.Primitives.Popup>|Área del submenú.|  
  
 Cuando se crea un <xref:System.Windows.Controls.ControlTemplate> para un <xref:System.Windows.Controls.MenuItem> , la plantilla podría contener un <xref:System.Windows.Controls.ItemsPresenter> dentro de <xref:System.Windows.Controls.ScrollViewer> . ( <xref:System.Windows.Controls.ItemsPresenter> Muestra cada elemento en <xref:System.Windows.Controls.MenuItem> ; <xref:System.Windows.Controls.ScrollViewer> habilita el desplazamiento dentro del control).  Si <xref:System.Windows.Controls.ItemsPresenter> no es el elemento secundario directo de <xref:System.Windows.Controls.ScrollViewer> , debe proporcionar el <xref:System.Windows.Controls.ItemsPresenter> nombre, `ItemsPresenter` .  
  
## <a name="menuitem-states"></a>Estados de MenuItem  
 En la tabla siguiente se enumeran los Estados visuales del <xref:System.Windows.Controls.MenuItem> control.  
  
|Nombre de VisualState|Nombre de VisualStateGroup|Descripción|  
|-|-|-|  
|Válido|ValidationStates|El control utiliza la <xref:System.Windows.Controls.Validation> clase y la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta es `false` .|  
|InvalidFocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta tiene `true` el foco.|  
|InvalidUnfocused|ValidationStates|La <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propiedad adjunta `true` tiene el control no tiene el foco.|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a>Ejemplo de menú y ControlTemplate de MenuItem  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.Menu> control.  
  
 [!code-xaml[ControlTemplateExamples#Menu](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.Controls.ControlTemplate> para el <xref:System.Windows.Controls.MenuItem> control.  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 En el ejemplo siguiente `MenuScrollViewer` se define, que se utiliza en el ejemplo anterior.  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 En los <xref:System.Windows.Controls.ControlTemplate> ejemplos se usa uno o varios de los siguientes recursos.  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Para ver un ejemplo completo, consulte [Aplicación de estilos con el ejemplo ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [Estilos y plantillas de controles](control-styles-and-templates.md)
- [Personalización de controles](control-customization.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Creación de una plantilla de un control](../../../desktop-wpf/themes/how-to-create-apply-template.md)
