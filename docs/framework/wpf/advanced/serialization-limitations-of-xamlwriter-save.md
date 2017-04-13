---
title: "Limitaciones en la serializaci&#243;n de XamlWriter.Save | Microsoft Docs"
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
  - "limitaciones de XamlWriter.Save"
  - "limitaciones en la serialización de XamlWriter.Save"
  - "XamlWriter.Save, limitaciones para la serialización de"
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Limitaciones en la serializaci&#243;n de XamlWriter.Save
El método [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] <xref:System.Windows.Markup.XamlWriter.Save%2A> se puede utilizar para serializar el contenido de una aplicación de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] como un archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Sin embargo, existen algunas limitaciones notables relativas a qué se serializa exactamente.  En este tema se documentan estas limitaciones y algunas consideraciones generales.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Run_Time__Not_Design_Time_Representation"></a>   
## Representación en tiempo de ejecución, no en tiempo de diseño  
 La filosofía básica de lo que se serializada mediante una llamada a <xref:System.Windows.Markup.XamlWriter.Save%2A> es que el resultado será una representación del objeto serializado en tiempo de ejecución.  Muchas propiedades en tiempo de diseño del archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] original pueden haberse optimizado o perdido para cuando el marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se carga como objetos en memoria, y no se conservan cuando se llama a <xref:System.Windows.Markup.XamlWriter.Save%2A> para realizar la serialización.  El resultado serializado es una representación efectiva del árbol lógico construido de la aplicación, pero no necesariamente del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] original que lo generó.  Estos problemas hace que sea sumamente difícil utilizar la serialización de <xref:System.Windows.Markup.XamlWriter.Save%2A> como parte de una superficie de diseño [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] extensa.  
  
<a name="Serialization_is_Self_Contained"></a>   
## Autonomía de la serialización  
 El resultado serializado de <xref:System.Windows.Markup.XamlWriter.Save%2A> es autónomo; todo lo que se serializa está contenido dentro de una sola página [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], con un elemento raíz único, sin referencia externa alguna a excepción de los [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)].  Por ejemplo, si en la página se hace referencia a recursos de los recursos de la aplicación, éstos aparecerán como si se tratara de un componente de la página serializada.  
  
<a name="Extension_References_are_Dereferenced"></a>   
## Desreferenciación de extensiones  
 El proceso de serialización Desreferenciará las referencias comunes a los objetos realizadas por diversos formatos de extensión de marcado, tales como `StaticResource` o `Binding`.  Estas referencias ya se han desreferenciado al crear los objetos en memoria en el tiempo de ejecución de la aplicación, y la lógica de <xref:System.Windows.Markup.XamlWriter.Save%2A> no repite el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] original para restaurar estas referencias en el resultado serializado.  Este hecho inmoviliza potencialmente todos los valores obtenidos de los recursos o enlazados a datos en el último valor utilizado por la representación en tiempo de ejecución, y únicamente se dispone de una capacidad limitada o indirecta para distinguir este valor de cualquier otro establecido localmente.  Las imágenes también se serializan como referencias a objeto a las imágenes tal cual existen en el proyecto, en lugar de cómo referencias originales del código fuente, con lo que se pierden los nombre de archivo y los [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] a los que se hiciera referencia originalmente.  Incluso los recursos declarados dentro de la propia página aparecen serializados en el punto donde se hizo referencia a ellos, en lugar de conservarse como una clave de una colección de recursos.  
  
<a name="Event_Handling_is_Not_Preserved"></a>   
## No se conserva el control de eventos  
 Cuando se serializan controladores de eventos que se agregan mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], estos no se conservan.  El marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sin código subyacente \(y sin el mecanismo relacionado x:Code\) no dispone de ninguna manera de serializar la lógica de procedimiento en tiempo de ejecución.  Dado que la serialización es autónoma y se limita al árbol lógico, no existe ningún medio para almacenar controladores de eventos.  Como resultado, los atributos de controladores de eventos, tanto el propio atributo como el valor de cadena que da nombre al controlador, se quitan del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de salida.  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>   
## Escenarios realistas para el uso de XAMLWriter.Save  
 Aunque las limitaciones que hemos enumerado son bastante importantes, existen varios escenarios en los que es adecuado utilizar <xref:System.Windows.Markup.XamlWriter.Save%2A> para la serialización.  
  
-   Salida vectorial o gráfica: la salida del área representada se puede utilizar para reproducir el mismo vector o gráfico al volver a cargarla.  
  
-   Documentos de texto enriquecido y dinámicos: el texto, el formato de todos los elementos y la contención de elementos en su seno se conservan en la salida.  Esto puede ser útil para los mecanismos afines a la funcionalidad del portapapeles.  
  
-   Conservar datos de objetos comerciales: si ha almacenado datos en elementos personalizados, tales como datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], los objetos comerciales se pueden perpetuar mediante la serialización siempre que sigan determinadas reglas básicas de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], como proporcionar constructores personalizados y conversión para valores de propiedades por referencia.