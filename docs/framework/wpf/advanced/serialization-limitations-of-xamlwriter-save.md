---
title: Limitaciones en la serialización de XamlWriter.Save
ms.date: 03/30/2017
helpviewer_keywords:
- XamlWriter.Save [WPF], serialization limitations of
- limitations of XamlWriter.Save
- serialization limitations of XamlWriter.Save
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
ms.openlocfilehash: 5b9141d5df40d74c4682f418a8fb089fddcfcaa9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740743"
---
# <a name="serialization-limitations-of-xamlwritersave"></a>Limitaciones en la serialización de XamlWriter.Save
La <xref:System.Windows.Markup.XamlWriter.Save%2A> de API se puede usar para serializar el contenido de una aplicación [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] como archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Pero existen algunas limitaciones notables relativas a qué se serializa exactamente. En este tema se documentan estas limitaciones y algunas consideraciones generales.  

<a name="Run_Time__Not_Design_Time_Representation"></a>   
## <a name="run-time-not-design-time-representation"></a>Representación en tiempo de ejecución, no en tiempo de diseño  
 La filosofía básica de lo que se serializa mediante una llamada a <xref:System.Windows.Markup.XamlWriter.Save%2A> es que el resultado será una representación del objeto que se está serializando, en tiempo de ejecución. Es posible que muchas propiedades en tiempo de diseño del archivo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] original ya estén optimizadas o perdidas en el momento en que se carga el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como objetos en memoria y no se conservan cuando se llama a <xref:System.Windows.Markup.XamlWriter.Save%2A> para serializar. El resultado serializado es una representación efectiva del árbol lógico construido de la aplicación, pero no necesariamente del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] original que lo ha generado. Estos problemas hacen que sea sumamente difícil usar la serialización <xref:System.Windows.Markup.XamlWriter.Save%2A> como parte de una amplia superficie de diseño [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
<a name="Serialization_is_Self_Contained"></a>   
## <a name="serialization-is-self-contained"></a>Autonomía de la serialización  
 La salida serializada de <xref:System.Windows.Markup.XamlWriter.Save%2A> es independiente; todo lo que se serializa se encuentra dentro de una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sola página, con un único elemento raíz y sin referencias externas que no sean los URI. Por ejemplo, si en la página se hace referencia a recursos de los recursos de la aplicación, estos aparecerán como si se tratara de un componente de la página serializada.  
  
<a name="Extension_References_are_Dereferenced"></a>   
## <a name="extension-references-are-dereferenced"></a>Desreferenciación de extensiones  
 El proceso de serialización desreferenciará las referencias comunes a los objetos realizadas por diversos formatos de extensión de marcado, como `StaticResource` o `Binding`. Ya se desreferenciaron en el momento en que se crearon los objetos en memoria en el tiempo de ejecución de la aplicación y la lógica de <xref:System.Windows.Markup.XamlWriter.Save%2A> no vuelve a visitar el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] original para restaurar estas referencias a la salida serializada. Esto inmoviliza potencialmente todos los valores obtenidos de los recursos o enlazados a datos en el último valor usado por la representación en tiempo de ejecución, y únicamente se dispone de una capacidad limitada o indirecta para distinguir este valor de cualquier otro establecido localmente. Las imágenes también se serializan como referencias de objeto a las imágenes tal como existen en el proyecto, en lugar de como referencias de origen originales, lo que pierde cualquier nombre de archivo o URI al que se hacía referencia originalmente. Incluso los recursos declarados dentro de la misma página aparecen serializados en el punto donde se ha hecho referencia a ellos, en lugar de conservarse como una clave de una colección de recursos.  
  
<a name="Event_Handling_is_Not_Preserved"></a>   
## <a name="event-handling-is-not-preserved"></a>No se conserva el control de eventos  
 Cuando se serializan controladores de eventos que se agregan mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], no se conservan. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sin código subyacente (y sin el mecanismo relacionado x:Code) no dispone de ninguna manera de serializar la lógica de procedimiento en tiempo de ejecución. Dado que la serialización es autónoma y se limita al árbol lógico, no existe ningún medio para almacenar los controladores de eventos. Como resultado, los atributos de controladores de eventos, tanto el propio atributo como el valor de cadena que da nombre al controlador, se quitan del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de salida.  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>   
## <a name="realistic-scenarios-for-use-of-xamlwritersave"></a>Escenarios realistas para el uso de XAMLWriter.Save  
 Aunque las limitaciones que se enumeran aquí son bastante sustanciales, todavía hay varios escenarios adecuados para usar <xref:System.Windows.Markup.XamlWriter.Save%2A> para la serialización.  
  
- Salida vectorial o gráfica: la salida del área representada se puede usar para reproducir el mismo vector o gráfico al volver a cargarla.  
  
- Documentos de texto enriquecido y dinámicos: el texto y el formato y la contención de todos los elementos se conservan en la salida. Esto puede ser útil para los mecanismos afines a la funcionalidad del Portapapeles.  
  
- Conservar los datos del objeto comercial: si se han almacenado datos en elementos personalizados, como datos XML, siempre y cuando los objetos comerciales sigan reglas de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] básicas, como proporcionar constructores y conversión personalizados para los valores de propiedad por referencia, estas empresas los objetos se pueden perpetuar a través de la serialización.
