---
title: Extensión de marcado TemplateBinding
ms.date: 03/30/2017
f1_keywords:
- TemplateBinding
- TemplateBindingExtension
helpviewer_keywords:
- XAML [WPF], TemplateBinding markup extension
- TemplateBinding markup extensions [WPF]
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
ms.openlocfilehash: d425d17405bc8241c3fd85c77c6672265a060900
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546925"
---
# <a name="templatebinding-markup-extension"></a>Extensión de marcado TemplateBinding
Vincula el valor de una propiedad de una plantilla de control para que sea el valor de otra propiedad del control con plantilla.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xml  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-attribute-usage-for-setter-property-in-template-or-style"></a>Uso de atributos XAML (para la propiedad Setter de una plantilla o estilo)  
  
```xml  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`propertyName`|Propiedad <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType> que se va establecer en la sintaxis del establecedor.|  
|`sourceProperty`|Otra propiedad de dependencia existente en el tipo con plantilla, especificada por el valor de <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.<br /><br /> O bien<br /><br /> Nombre de propiedad "relacionada" que se define por un tipo diferente del tipo de destino que se va a convertir en un tipo con plantilla. En realidad, se trata de un objeto <xref:System.Windows.PropertyPath>. Vea [sintaxis de PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).|  
  
## <a name="remarks"></a>Comentarios  
 A `TemplateBinding` es una forma optimizada de un [enlace](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) para escenarios de plantilla, análogos a un `Binding` construidos con `{Binding RelativeSource={RelativeSource TemplatedParent}}`. `TemplateBinding` siempre es un enlace unidireccional, aunque las propiedades implicadas establezcan por defecto un enlace bidireccional. Ambas propiedades implicadas deben ser propiedades de dependencia.  
  
 [RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) es otra extensión de marcado que a veces se usa en conjunción con o en lugar de `TemplateBinding` con el fin de realizar el enlace de la propiedad relativa dentro de una plantilla.  
  
 Describir plantillas de control como un concepto no se trata aquí; Para obtener más información, consulte [plantillas y estilos de Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `TemplateBinding` se asigna como valor de <xref:System.Windows.TemplateBindingExtension.Property%2A> de la clase de extensión <xref:System.Windows.TemplateBindingExtension> subyacente.  
  
 La sintaxis de elementos de objeto es posible, pero no se muestra porque no tiene ninguna aplicación en el mundo real. `TemplateBinding` se emplea para rellenar los valores dentro de los establecedores, mediante expresiones evaluadas, y el uso de la sintaxis de elementos de objeto para que `TemplateBinding` rellene la sintaxis de elementos de propiedad de `<Setter.Property>` aplica un grado de detalle innecesario.  
  
 `TemplateBinding` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.TemplateBindingExtension.Property%2A> como un par de propiedad=valor:  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales. Dado que `TemplateBinding` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.  
  
 En el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementación del procesador XAML, el control para esta extensión de marcado se define por la <xref:System.Windows.TemplateBindingExtension> clase.  
  
 `TemplateBinding` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones de marcado de XAML utilizan la `{` y `}` caracteres en su sintaxis de atributo, que es la convención que permite que un procesador XAML reconozca que una extensión de marcado debe procesar el atributo. Para más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Style>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [RelativeSource (extensión de marcado)](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)  
 [Binding (extensión de marcado)](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)
