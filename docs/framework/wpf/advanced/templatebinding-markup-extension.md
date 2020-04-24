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
ms.openlocfilehash: 8c631a5a78db90187f0375181d4d4d1832159b7d
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646170"
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
|`sourceProperty`|Otra propiedad de dependencia existente en el tipo con plantilla, especificada por el valor de <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=nameWithType>.<br /><br /> O bien<br /><br /> Nombre de propiedad "relacionada" que se define por un tipo diferente del tipo de destino que se va a convertir en un tipo con plantilla. En realidad, se trata de un objeto <xref:System.Windows.PropertyPath>. Consulte [Sintaxis XAML PropertyPath](propertypath-xaml-syntax.md).|  
  
## <a name="remarks"></a>Observaciones  
 A `TemplateBinding` es una forma optimizada de un [enlace](binding-markup-extension.md) para `Binding` escenarios `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=OneWay}`de plantilla, análogo a un construido con . `TemplateBinding` siempre es un enlace unidireccional, aunque las propiedades implicadas establezcan por defecto un enlace bidireccional. Ambas propiedades implicadas deben ser propiedades de dependencia. Para lograr el enlace bidireccional a un elemento primario con `{Binding RelativeSource={RelativeSource TemplatedParent}, Mode=TwoWay, Path=MyDependencyProperty}`plantilla, utilice la siguiente instrucción de enlace en su lugar.
  
 [RelativeSource](relativesource-markupextension.md) es otra extensión de marcado que a `TemplateBinding` veces se usa junto con o en lugar de para realizar el enlace de propiedad relativa dentro de una plantilla.  
  
 La descripción de plantillas de control como un concepto no se trata aquí; Para obtener más información, consulte [Estilos de control y plantillas](../controls/control-styles-and-templates.md).  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado. El token de cadena que se proporciona después de la cadena de identificador `TemplateBinding` se asigna como valor de <xref:System.Windows.TemplateBindingExtension.Property%2A> de la clase de extensión <xref:System.Windows.TemplateBindingExtension> subyacente.  
  
 La sintaxis de elementos de objeto es posible, pero no se muestra porque no tiene ninguna aplicación en el mundo real. `TemplateBinding` se emplea para rellenar los valores dentro de los establecedores, mediante expresiones evaluadas, y el uso de la sintaxis de elementos de objeto para que `TemplateBinding` rellene la sintaxis de elementos de propiedad de `<Setter.Property>` aplica un grado de detalle innecesario.  
  
 `TemplateBinding` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.TemplateBindingExtension.Property%2A> como un par de propiedad=valor:  
  
```xml  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales. Dado que `TemplateBinding` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.  
  
 En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la implementación del procesador XAML, la <xref:System.Windows.TemplateBindingExtension> clase define el control de esta extensión de marcado.  
  
 `TemplateBinding` es una extensión de marcado. Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades. Todas las extensiones `{` de `}` marcado en XAML usan los caracteres y en su sintaxis de atributo, que es la convención por la que un procesador XAML reconoce que una extensión de marcado debe procesar el atributo. Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.ControlTemplate>
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md)
- [Extensión de marcado RelativeSource](relativesource-markupextension.md)
- [Enlazar extensión de marcado](binding-markup-extension.md)
