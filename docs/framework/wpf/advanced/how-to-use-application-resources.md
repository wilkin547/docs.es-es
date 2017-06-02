---
title: "C&#243;mo: Usar recursos de aplicaciones | Microsoft Docs"
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
  - "recursos de la aplicación"
  - "recursos, recursos de la aplicación"
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Usar recursos de aplicaciones
En este ejemplo se muestra cómo utilizar los recursos de aplicaciones.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra un archivo de definición de aplicación.  El archivo de definición de aplicación define una sección de recursos \(un valor para la propiedad <xref:System.Windows.Application.Resources%2A>\).  Los recursos definidos en el nivel de aplicación están accesibles para todas las demás páginas que forman parte de la aplicación.  En este caso, el recurso es un estilo declarado.  Dado que un estilo completo que incluye una plantilla de control puede ser largo, en este ejemplo se omite la plantilla de control que se define dentro del establecedor de la propiedad <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> del estilo.  
  
 [!code-xml[ResourcesApplication#PreTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xml[ResourcesApplication#PostTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 En el ejemplo siguiente se muestra una página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que hace referencia al recurso del nivel de aplicación definido en el ejemplo anterior.  Se hace referencia al recurso mediante una [Extensión de marcado StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) que especifica la clave de recurso única para el recurso solicitado.  No se encuentra ningún recurso cuya clave sea "GelButton" en la página actual, por lo que el ámbito de búsqueda de recurso del recurso solicitado continúa más allá de la página actual hasta los recursos definidos en el nivel de aplicación.  
  
 [!code-xml[ResourcesApplication#ConsumingPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## Vea también  
 [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [Información general sobre la administración de aplicaciones](../../../../docs/framework/wpf/app-development/application-management-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)