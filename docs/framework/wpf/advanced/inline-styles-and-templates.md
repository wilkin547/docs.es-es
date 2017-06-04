---
title: "Estilos y plantillas insertados | Microsoft Docs"
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
  - "estilos en línea"
  - "plantillas en línea"
  - "estilos, inline"
  - "plantillas, inline"
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Estilos y plantillas insertados
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona objetos <xref:System.Windows.Style> y objetos de plantilla \(subclases de <xref:System.Windows.FrameworkTemplate>\) como una manera de definir el aspecto visual de un elemento en los recursos, para poder utilizarlos varias veces.  Por esta razón, los atributos de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que aceptan los tipos <xref:System.Windows.Style> y <xref:System.Windows.FrameworkTemplate> casi siempre realizan referencias de recursos a estilos y plantillas existentes, en lugar de definir otros nuevos insertados.  
  
## Limitaciones de los estilos y las plantillas insertados  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], las propiedades de estilos y plantillas se pueden establecer técnicamente de dos maneras.  Puede utilizar la sintaxis de atributo para hacer referencia a un estilo definido dentro de un recurso, por ejemplo, `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.  O bien, puede utilizar la sintaxis de elementos de propiedad para definir un estilo insertado, por ejemplo:  
  
 `<` *objeto* `>`  
  
 `<` *objeto* `.Style>`  
  
 `<` `Style`  `.../>`  
  
 `</` *objeto* `.Style>`  
  
 `</` *objeto* `>`  
  
 El uso de atributos es mucho más común.  Un estilo que se define insertado y no se define en los recursos necesariamente queda limitado al ámbito del elemento contenedor y no se puede reutilizar con facilidad porque carece de clave de recurso.  En general, un estilo definido como recurso es más versátil y útil, y está más en línea con el principio general del modelo de programación de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], consistente en separar la lógica de programación, en el código, de la de diseño, en el marcado.  
  
 Normalmente, no hay ninguna razón para establecer un estilo o una plantilla insertados, aunque únicamente se pretendan utilizar en esa ubicación.  La mayoría de los elementos que pueden tomar un estilo o una plantilla también admiten una propiedad de contenido y un modelo de contenido.  Aunque vaya a usar el árbol lógico que cree mediante estilos o plantillas una sola vez, resultaría incluso más fácil rellenar esa propiedad de contenido con los elementos secundarios equivalentes en el marcado directo.  De este modo se omitirían totalmente los mecanismos de plantillas y estilos.  
  
 También son posibles para los estilos y las plantillas otras sintaxis habilitadas por las extensiones de marcado que devuelven un objeto.  Dos de estas extensiones con escenarios posibles son [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) y <xref:System.Windows.Data.Binding>.  
  
## Vea también  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)