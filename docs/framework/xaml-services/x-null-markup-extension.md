---
title: "x:Null Markup Extension | Microsoft Docs"
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
  - "NullExtension"
  - "x:NullExtension"
  - "x:Null"
  - "Null"
  - "xNull"
helpviewer_keywords: 
  - "Null markup extension in XAML [XAML Services]"
  - "x:Null markup extension [XAML Services]"
  - "XAML [XAML Services], x:Null markup extension"
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
caps.latest.revision: 20
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 20
---
# x:Null Markup Extension
Especifica `null` como valor para un miembro XAML.  
  
## Uso de atributos XAML  
  
```  
<object property="{x:Null}" .../>  
```  
  
## Comentarios  
 La palabra clave para una referencia nula  en [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] y [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] es NULL.  La palabra clave [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] para una referencia null es `Nothing`, pero siempre utiliza `{x:Null}` como la utilización XAML sin tener en cuenta que el lenguaje de código subyacente que se asocie a XAML.  
  
 La extensión de marcado `x:Null` no tiene ninguna propiedad que se pueda establecer.  
  
 Con frecuencia, una utilización de null está asociada a la exposición de miembro XAML de un valor <xref:System.Nullable%601> de CLR.  
  
 La extensión de marcado `x:Null`, al igual que todas las extensiones de marcado XAML, usa llaves \(`{,}`\) a fin de permitir, mediante secuencias de escape, el control de valores de atributos que no sean literales o referencias del controlador de eventos.  La sintaxis de atributo es la que se usa más a menudo con esta extensión de marcado.  Una sintaxis de elementos de objeto `<x:Null />` es técnicamente posible, pero raramente se usa porque la extensión de marcado `x:Null` no tiene ningún parámetro posicional ni argumentos de construcción.  
  
 Para obtener información sobre las extensiones de marcado, vea [Extensiones de marcado y XAML de WPF](../../../ocs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 La clase <xref:System.Windows.Markup.NullExtension> define el control para esta extensión de marcado en servicios XAML de .NET Framework.  
  
## Notas de uso de WPF  
 Observe que `null` no es necesariamente el valor inicial no establecido para una propiedad de dependencia de tipo de referencia.  El valor predeterminado inicial puede variar para cada propiedad de dependencia, y puede estar basado en metadatos específicos de la propiedad.  Muchas propiedades de dependencia no aceptan el valor `null`, mediante marcado ni mediante código, debido a sus implementaciones de devolución de llamada de validación.  Para obtener más información sobre las propiedades de dependencia, vea [Información general sobre las propiedades de dependencia](../../../ocs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## Vea también  
 <xref:System.Windows.DependencyProperty.UnsetValue>   
 [Información general sobre XAML \(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Extensiones de marcado y XAML de WPF](../../../ocs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)