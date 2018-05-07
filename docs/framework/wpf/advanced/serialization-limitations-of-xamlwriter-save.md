---
title: Limitaciones en la serialización de XamlWriter.Save
ms.date: 03/30/2017
helpviewer_keywords:
- XamlWriter.Save [WPF], serialization limitations of
- limitations of XamlWriter.Save
- serialization limitations of XamlWriter.Save
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
ms.openlocfilehash: cbe8d517b8794f6aae7190457a077422d235acb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="serialization-limitations-of-xamlwritersave"></a>Limitaciones en la serialización de XamlWriter.Save
El [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] <xref:System.Windows.Markup.XamlWriter.Save%2A> puede usarse para serializar el contenido de un [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] aplicación como un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo. Pero existen algunas limitaciones notables relativas a qué se serializa exactamente. En este tema se documentan estas limitaciones y algunas consideraciones generales.  
  
 
  
<a name="Run_Time__Not_Design_Time_Representation"></a>   
## <a name="run-time-not-design-time-representation"></a>Representación en tiempo de ejecución, no en tiempo de diseño  
 La filosofía básica de lo que se serializa mediante una llamada a <xref:System.Windows.Markup.XamlWriter.Save%2A> es que el resultado será una representación del objeto que se está serializando en tiempo de ejecución. Muchas propiedades en tiempo de diseño de la versión original [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo ya esté optimizado o perdido por el tiempo que el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se cargan como objetos en memoria y no se conservan cuando se llama a <xref:System.Windows.Markup.XamlWriter.Save%2A> para serializar. El resultado serializado es una representación efectiva del árbol lógico construido de la aplicación, pero no necesariamente del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] original que lo ha generado. Estos problemas dificultan en gran medida usar la <xref:System.Windows.Markup.XamlWriter.Save%2A> serialización como parte de un amplio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] superficie de diseño.  
  
<a name="Serialization_is_Self_Contained"></a>   
## <a name="serialization-is-self-contained"></a>Autonomía de la serialización  
 El resultado serializado de <xref:System.Windows.Markup.XamlWriter.Save%2A> son independientes entre sí; todo lo que se serializa se encuentra dentro de un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sola página, con un elemento raíz único y no hay referencias externas distinto de [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)]. Por ejemplo, si en la página se hace referencia a recursos de los recursos de la aplicación, estos aparecerán como si se tratara de un componente de la página serializada.  
  
<a name="Extension_References_are_Dereferenced"></a>   
## <a name="extension-references-are-dereferenced"></a>Desreferenciación de extensiones  
 El proceso de serialización desreferenciará las referencias comunes a los objetos realizadas por diversos formatos de extensión de marcado, como `StaticResource` o `Binding`. Estos se desreferencia ya en el momento en la memoria de objetos creados por el tiempo de ejecución de la aplicación, y el <xref:System.Windows.Markup.XamlWriter.Save%2A> lógica no volver a visitar el original [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para restaurar estas referencias en el resultado serializado. Esto inmoviliza potencialmente todos los valores obtenidos de los recursos o enlazados a datos en el último valor usado por la representación en tiempo de ejecución, y únicamente se dispone de una capacidad limitada o indirecta para distinguir este valor de cualquier otro establecido localmente. Las imágenes también se serializan como referencias de objeto a las imágenes tal cual existen en el proyecto, en lugar de como referencias originales del código fuente, con lo que se pierden los nombre de archivo o [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] a los que se hizo referencia originalmente. Incluso los recursos declarados dentro de la misma página aparecen serializados en el punto donde se ha hecho referencia a ellos, en lugar de conservarse como una clave de una colección de recursos.  
  
<a name="Event_Handling_is_Not_Preserved"></a>   
## <a name="event-handling-is-not-preserved"></a>No se conserva el control de eventos  
 Cuando se serializan controladores de eventos que se agregan mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], no se conservan. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sin código subyacente (y sin el mecanismo relacionado x:Code) no dispone de ninguna manera de serializar la lógica de procedimiento en tiempo de ejecución. Dado que la serialización es autónoma y se limita al árbol lógico, no existe ningún medio para almacenar los controladores de eventos. Como resultado, los atributos de controladores de eventos, tanto el propio atributo como el valor de cadena que da nombre al controlador, se quitan del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de salida.  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>   
## <a name="realistic-scenarios-for-use-of-xamlwritersave"></a>Escenarios realistas para el uso de XAMLWriter.Save  
 Aunque las limitaciones enumeran aquí son bastante importantes, todavía hay varios escenarios adecuados para el uso de <xref:System.Windows.Markup.XamlWriter.Save%2A> para la serialización.  
  
-   Salida vectorial o gráfica: la salida del área representada se puede usar para reproducir el mismo vector o gráfico al volver a cargarla.  
  
-   Documentos de texto enriquecido y dinámicos: el texto y el formato y la contención de todos los elementos se conservan en la salida. Esto puede ser útil para los mecanismos afines a la funcionalidad del Portapapeles.  
  
-   Conservación de datos de objetos comerciales: si se han almacenado datos en elementos personalizados, tales como datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], los objetos comerciales se pueden perpetuar mediante la serialización siempre que sigan determinadas reglas básicas de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], como proporcionar constructores personalizados y conversión para valores de propiedades por referencia.
