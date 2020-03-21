---
title: Limitaciones en la serialización de XamlWriter.Save
ms.date: 03/30/2017
helpviewer_keywords:
- XamlWriter.Save [WPF], serialization limitations of
- limitations of XamlWriter.Save
- serialization limitations of XamlWriter.Save
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
ms.openlocfilehash: 96e917898320fb5d49f4e7dfc27daa7750af9d41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174373"
---
# <a name="serialization-limitations-of-xamlwritersave"></a>Limitaciones en la serialización de XamlWriter.Save
La <xref:System.Windows.Markup.XamlWriter.Save%2A> API se puede utilizar para [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] serializar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] el contenido de una aplicación como un archivo. Pero existen algunas limitaciones notables relativas a qué se serializa exactamente. En este tema se documentan estas limitaciones y algunas consideraciones generales.  

<a name="Run_Time__Not_Design_Time_Representation"></a>
## <a name="run-time-not-design-time-representation"></a>Representación en tiempo de ejecución, no en tiempo de diseño  
 La filosofía básica de lo que <xref:System.Windows.Markup.XamlWriter.Save%2A> se serializa mediante una llamada a es que el resultado será una representación del objeto que se serializa, en tiempo de ejecución. Muchas propiedades en tiempo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de diseño del archivo original ya [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] pueden optimizarse o perderse en el momento <xref:System.Windows.Markup.XamlWriter.Save%2A> en que se carga como objetos en memoria y no se conservan cuando se llama a serializar. El resultado serializado es una representación efectiva del árbol lógico construido de la aplicación, pero no necesariamente del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] original que lo ha generado. Estos problemas hacen que sea <xref:System.Windows.Markup.XamlWriter.Save%2A> extremadamente difícil utilizar [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] la serialización como parte de una amplia superficie de diseño.  
  
<a name="Serialization_is_Self_Contained"></a>
## <a name="serialization-is-self-contained"></a>Autonomía de la serialización  
 La salida serializada de <xref:System.Windows.Markup.XamlWriter.Save%2A> es independiente; todo lo que se serializa [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] está contenido dentro de una sola página, con un único elemento raíz y sin referencias externas que no sean URI. Por ejemplo, si en la página se hace referencia a recursos de los recursos de la aplicación, estos aparecerán como si se tratara de un componente de la página serializada.  
  
<a name="Extension_References_are_Dereferenced"></a>
## <a name="extension-references-are-dereferenced"></a>Desreferenciación de extensiones  
 El proceso de serialización desreferenciará las referencias comunes a los objetos realizadas por diversos formatos de extensión de marcado, como `StaticResource` o `Binding`. Estos ya se desreferenciaron en el momento en que <xref:System.Windows.Markup.XamlWriter.Save%2A> el tiempo de ejecución [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de la aplicación creó objetos en memoria y la lógica no vuelve a visitar el original para restaurar dichas referencias a la salida serializada. Esto inmoviliza potencialmente todos los valores obtenidos de los recursos o enlazados a datos en el último valor usado por la representación en tiempo de ejecución, y únicamente se dispone de una capacidad limitada o indirecta para distinguir este valor de cualquier otro establecido localmente. Las imágenes también se serializan como referencias de objeto a imágenes tal como existen en el proyecto, en lugar de como referencias de origen originales, lo que pierde cualquier nombre de archivo o URI al que se hizo referencia originalmente. Incluso los recursos declarados dentro de la misma página aparecen serializados en el punto donde se ha hecho referencia a ellos, en lugar de conservarse como una clave de una colección de recursos.  
  
<a name="Event_Handling_is_Not_Preserved"></a>
## <a name="event-handling-is-not-preserved"></a>No se conserva el control de eventos  
 Cuando se serializan controladores de eventos que se agregan mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], no se conservan. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sin código subyacente (y sin el mecanismo relacionado x:Code) no dispone de ninguna manera de serializar la lógica de procedimiento en tiempo de ejecución. Dado que la serialización es autónoma y se limita al árbol lógico, no existe ningún medio para almacenar los controladores de eventos. Como resultado, los atributos de controladores de eventos, tanto el propio atributo como el valor de cadena que da nombre al controlador, se quitan del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de salida.  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>
## <a name="realistic-scenarios-for-use-of-xamlwritersave"></a>Escenarios realistas para el uso de XAMLWriter.Save  
 Aunque las limitaciones enumeradas aquí son bastante sustanciales, <xref:System.Windows.Markup.XamlWriter.Save%2A> todavía hay varios escenarios apropiados para usar para la serialización.  
  
- Salida vectorial o gráfica: la salida del área representada se puede usar para reproducir el mismo vector o gráfico al volver a cargarla.  
  
- Documentos de texto enriquecido y dinámicos: el texto y el formato y la contención de todos los elementos se conservan en la salida. Esto puede ser útil para los mecanismos afines a la funcionalidad del Portapapeles.  
  
- Conservación de datos de objetos de negocio: si ha almacenado datos en elementos personalizados, como datos XML, siempre que los objetos de negocio sigan reglas básicas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como proporcionar constructores personalizados y conversión para los valores de propiedad por referencia, estos objetos de negocio se pueden perpetuar mediante la serialización.
