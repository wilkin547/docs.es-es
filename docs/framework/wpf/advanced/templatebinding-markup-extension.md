---
title: "Extensi&#243;n de marcado TemplateBinding | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TemplateBinding"
  - "TemplateBindingExtension"
helpviewer_keywords: 
  - "TemplateBinding (extensión de marcado)"
  - "XAML, TemplateBinding (extensión de marcado)"
ms.assetid: 1d25bbfc-dbc2-499d-9f12-419d23d4ac6a
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Extensi&#243;n de marcado TemplateBinding
Vincula el valor de una propiedad de una plantilla de control para que sea el valor de otra propiedad del control con plantilla.  
  
## Uso de atributos XAML  
  
```  
<object property="{TemplateBinding sourceProperty}" .../>  
```  
  
## Uso de atributos XAML \(para la propiedad Setter de una plantilla o estilo\)  
  
```  
<Setter Property="propertyName" Value="{TemplateBinding sourceProperty}" .../>  
```  
  
## Valores XAML  
  
|||  
|-|-|  
|`propertyName`|Propiedad <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=fullName> que se va establecer en la sintaxis del establecedor.|  
|`sourceProperty`|Otra propiedad de dependencia existente en el tipo con plantilla, especificada por el valor de <xref:System.Windows.DependencyProperty.Name%2A?displayProperty=fullName>.<br /><br /> – O bien –<br /><br /> Nombre de propiedad "relacionada" que se define por un tipo diferente del tipo de destino que se va a convertir en un tipo con plantilla.  En realidad, se trata de un objeto <xref:System.Windows.PropertyPath>.  Vea [Sintaxis de PropertyPath de XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).|  
  
## Comentarios  
 `TemplateBinding` es una forma optimizada de [enlace](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) para los escenarios de plantilla, similar a la instrucción `Binding` construida con `{Binding RelativeSource={RelativeSource TemplatedParent}}`.  `TemplateBinding` siempre es un enlace unidireccional, aunque las propiedades implicadas establezcan por defecto un enlace bidireccional.  Ambas propiedades implicadas deben ser propiedades de dependencia.  
  
 [RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md) es otra extensión de marcado que se utiliza a veces en combinación con `TemplateBinding` o en su lugar para realizar enlaces de propiedades relativos dentro de una plantilla.  
  
 La descripción del concepto de las plantillas de control no se incluye aquí; para obtener más información vea [Estilos y plantillas de controles](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
 La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado.  El token de cadena que se proporciona después de la cadena de identificador `TemplateBinding` se asigna como valor de <xref:System.Windows.TemplateBindingExtension.Property%2A> de la clase de extensión <xref:System.Windows.TemplateBindingExtension> subyacente.  
  
 La sintaxis de elementos de objeto es posible, pero no se muestra porque no tiene ninguna aplicación en el mundo real.  `TemplateBinding` se emplea para rellenar los valores dentro de los establecedores, mediante expresiones evaluadas, y el uso de la sintaxis de elementos de objeto para que `TemplateBinding` rellene la sintaxis de elementos de propiedad de `<Setter.Property>` aplica un grado de detalle innecesario.  
  
 `TemplateBinding` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.TemplateBindingExtension.Property%2A> como un par de propiedad\=valor:  
  
```  
<object property="{TemplateBinding Property=sourceProperty}" .../>  
```  
  
 El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales.  Dado que `TemplateBinding` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.  
  
 La clase <xref:System.Windows.TemplateBindingExtension> define el control para esta extensión de marcado en la implementación del procesador XAML de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 `TemplateBinding` es una extensión de marcado.  Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.  Todas las extensiones de marcado de XAML utilizan los caracteres `{` y `}` en su sintaxis de atributo, que es la convención que permite que un procesador de XAML reconozca que el atributo se debe procesar mediante una extensión de marcado.  Para obtener más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## Vea también  
 <xref:System.Windows.Style>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Extensión de marcado RelativeSource](../../../../docs/framework/wpf/advanced/relativesource-markupextension.md)   
 [Enlazar extensión de marcado](../../../../docs/framework/wpf/advanced/binding-markup-extension.md)