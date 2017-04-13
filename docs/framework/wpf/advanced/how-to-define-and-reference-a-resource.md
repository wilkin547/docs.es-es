---
title: "C&#243;mo: Definir y hacer referencia a un recurso | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "definir recursos"
  - "hacer referencia a recursos"
  - "recursos, definir"
  - "recursos, hacer referencia"
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Definir y hacer referencia a un recurso
En este ejemplo se muestra cómo definir un recurso y hacer referencia a él utilizando un atributo en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
## Ejemplo  
 En el ejemplo siguiente se definen dos tipos de recursos: un recurso <xref:System.Windows.Media.SolidColorBrush> y varios recursos <xref:System.Windows.Style>.  El recurso <xref:System.Windows.Media.SolidColorBrush>`MyBrush` se utiliza para proporcionar el valor de varias propiedades, cada una de las cuales toma un valor de tipo <xref:System.Windows.Media.Brush>.  Cada uno de los recursos <xref:System.Windows.Style> \(`PageBackground`, `TitleText` y `Label`\) está destinado a un tipo de control determinado.  Los estilos establecen varias propiedades diferentes para los controles de destino, cuando se hace referencia a ese recurso de estilo por su clave de recurso y se utiliza para establecer la propiedad <xref:System.Windows.FrameworkElement.Style%2A> de varios elementos de control concretos definidos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Observe que una de las propiedades de de los establecedores \(setters\) del estilo `Label` también hace referencia al recurso `MyBrush` definido anteriormente.  Se trata de una técnica común, pero es importante recordar que los recursos se analizan y escriben en un diccionario de recursos en el orden en que se indican.  También se solicitan los recursos en el orden en que se encuentran en el diccionario si se utiliza [Extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) para hacer referencia a ellos desde el interior de otro recurso.  Asegúrese de que todos los recursos a los que haga referencia se hayan definido en la colección de recursos antes del punto en que se solicita ese recurso.  Si es necesario, puede omitir el orden estricto de creación de referencias a recursos utilizando la [Extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) para hacer referencia lugar al recurso en tiempo de ejecución, pero debe tener en cuenta que esta técnica de DynamicResource influye en el rendimiento.  Para obtener información detallada, vea [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 [!code-xml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## Vea también  
 [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)