---
title: "Almacenamiento y serialización de documentos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 'serialization of documents [WPF], , '
- documents [WPF], storage
- documents [WPF], serialization
ms.assetid: 4839cd87-e206-4571-803f-0200098ad37b
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9a232e1e2557bf1ecc6bb5f27f941e03a204aec6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="document-serialization-and-storage"></a>Almacenamiento y serialización de documentos
[!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] proporciona un entorno eficaz para crear y mostrar documentos de alta calidad.  Las características mejoradas que admiten tanto documentos fijos como documentos dinámicos y los controles avanzados de visualización, combinados con las eficaces capacidades gráficas 2D y 3D, llevan a las aplicaciones [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] a un nuevo nivel de calidad y experiencia del usuario.  La capacidad de administrar con flexibilidad una representación en memoria de un documento es una característica clave de [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)], y poder guardar y cargar documentos de manera eficaz desde un almacén de datos es una necesidad de casi cualquier aplicación.  El proceso de convertir un documento de una representación en memoria interna a un almacén de datos externo se denomina “serialización”.  El proceso inverso de leer un almacén de datos y volver a crear la instancia en memoria original se denomina “deserialización”.  
  
 
  
<a name="AboutSerialization"></a>   
## <a name="about-document-serialization"></a>Acerca de la serialización de documentos  
 Lo ideal es que el proceso de serialización y deserialización de un documento desde la memoria y de vuelta hacia esta sea transparente para la aplicación.  La aplicación llama a un método serializador de "escritura" para guardar el documento, mientras que un método deserializador de "lectura" obtiene acceso al almacén de datos y vuelve a crear la instancia original en memoria.  En general, la aplicación no se encarga del formato específico en que se almacenan los datos, siempre que el proceso de serialización y deserialización vuelva a crear el documento en su forma original.  
  
 Las aplicaciones suelen proporcionar varias opciones de serialización que permiten al usuario guardar documentos en distintos soportes o en un formato diferente.  Por ejemplo, una aplicación podría ofrecer la opción "Guardar como" para almacenar un documento en un archivo de disco, una base de datos o un servicio web.  De forma similar, diferentes serializadores podrían almacenar el documento en formatos diferentes, por ejemplo, HTML, RTF, XML, XPS o, como alternativa, un formato de otro fabricante.  Para la aplicación, la serialización define una interfaz que aísla los detalles del soporte de almacenamiento dentro de la implementación de cada serializador concreto.  Además de las ventajas de encapsular los detalles de almacenamiento, el [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] <xref:System.Windows.Documents.Serialization> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] proporcionan varias otras características importantes.  
  
### <a name="features-of-net-framework-30-document-serializers"></a>Características de los serializadores de documentos de .NET Framework 3.0  
  
-   El acceso directo a los objetos de documento de alto nivel (árbol lógico y elementos visuales) permite el almacenamiento eficiente de contenido paginado, elementos 2D o 3D, imágenes, elementos multimedia, hipervínculos, anotaciones y otro contenido de compatibilidad.  
  
-   Funcionamiento sincrónico y asincrónico.  
  
-   Compatibilidad con los serializadores de complemento con funciones mejoradas:  
  
    -   Acceso a todo el sistema para su uso por todas las aplicaciones [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)].  
  
    -   Capacidad sencilla de detectar complementos de aplicaciones.  
  
    -   Implementación, instalación y actualización sencillas de complementos personalizados de terceros.  
  
    -   Compatibilidad de interfaz de usuario para opciones y configuración personalizadas en tiempo de ejecución.  
  
### <a name="xps-print-path"></a>Ruta de impresión XPS  
 La ruta de impresión de [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] proporciona también un mecanismo extensible para escribir documentos a través de la salida impresa.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] funciona como formato de archivo de documento y es el formato nativo de cola de impresión para [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)].  Los documentos de [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] pueden enviarse directamente a impresoras compatibles con [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] sin necesidad de convertirlos a un formato intermedio.  Consulte la [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md) para obtener información adicional sobre las capacidades y opciones de salida de la ruta de impresión.  
  
<a name="PluginSerializers"></a>   
## <a name="plug-in-serializers"></a>Serializadores de complemento  
 El <xref:System.Windows.Documents.Serialization> API proporcionan compatibilidad para los serializadores de complemento y serializadores vinculados que se instalan por separado de la aplicación, enlazar en tiempo de ejecución y se tiene acceso mediante la <xref:System.Windows.Documents.Serialization.SerializerProvider> mecanismo de detección.  Los serializadores de complemento proporcionan ventajas mejoradas de facilidad de implementación y uso en todo el sistema.  Los serializadores vinculados también pueden implementarse para entornos de confianza parcial, como [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)], donde no se tiene acceso a los serializadores de complemento.  Vincular los serializadores, que se basan en una implementación derivada de la <xref:System.Windows.Documents.Serialization.SerializerWriter> clase, que se compila y se vincula directamente en la aplicación.  Tanto los serializadores de complemento como los serializadores vinculados funcionan mediante métodos y eventos públicos idénticos que facilitan el uso de uno o ambos tipos de serializadores en la misma aplicación.  
  
 Los serializadores de complemento ayudan a los desarrolladores de aplicaciones, al proporcionar extensibilidad a nuevos diseños de almacenamiento y formatos de archivo sin tener que programar directamente para cada formato potencial en tiempo de compilación.  Los serializadores de complemento también benefician a los desarrolladores externos, al proporcionar un medio estandarizado para implementar, instalar y actualizar complementos accesibles por el sistema para formatos de archivo personalizados o de propietario.  
  
### <a name="using-a-plug-in-serializer"></a>Usar un serializador de complemento  
 Los serializadores de complemento son fáciles de usar.  El <xref:System.Windows.Documents.Serialization.SerializerProvider> clase enumera un <xref:System.Windows.Documents.Serialization.SerializerDescriptor> de objeto para cada complemento instalado en el sistema.  El <xref:System.Windows.Documents.Serialization.SerializerDescriptor.IsLoadable%2A> propiedad filtra los complementos instalados según la configuración actual y comprueba que el serializador se puede cargar y utilizado por la aplicación.  El <xref:System.Windows.Documents.Serialization.SerializerDescriptor> también proporciona otras propiedades, como <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DisplayName%2A> y <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DefaultFileExtension%2A>, que la aplicación puede utilizar para solicitar al usuario en la selección de un serializador para un formato de salida disponible.  Se proporciona un serializador de complemento predeterminado para [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] con [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)], que siempre se enumera.  Cuando el usuario selecciona un formato de salida, el <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> método se utiliza para crear un <xref:System.Windows.Documents.Serialization.SerializerWriter> para el formato específico.  El <xref:System.Windows.Documents.Serialization.SerializerWriter>.<xref:System.Windows.Documents.Serialization.SerializerWriter.Write%2A> , a continuación, se puede llamar el método para el flujo de documento en el almacén de datos de salida.  
  
 En el ejemplo siguiente se muestra una aplicación que utiliza el <xref:System.Windows.Documents.Serialization.SerializerProvider> método en una propiedad "PlugInFileFilter".  PlugInFileFilter enumera los complementos instalados y genera una cadena de filtro con las opciones de archivo disponibles para un <xref:Microsoft.Win32.SaveFileDialog>.  
  
 [!code-csharp[DocumentSerialize#DocSerializeFileFilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializefilefilter)]  
  
 Después de un nombre de archivo de salida se ha seleccionado por el usuario, en el ejemplo siguiente se muestra el uso de la <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> método utilizado para almacenar un documento determinado en un formato especificado.  
  
 [!code-csharp[DocumentSerialize#DocSerializePlugIn](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializeplugin)]  
  
<a name="InstallingPluginSerializers"></a>   
### <a name="installing-plug-in-serializers"></a>Instalar serializadores de complemento  
 La <xref:System.Windows.Documents.Serialization.SerializerProvider> clase proporciona la interfaz de aplicación de nivel superior para la detección de serializador del complemento y acceso.  <xref:System.Windows.Documents.Serialization.SerializerProvider>Busca y proporciona una lista de los serializadores que están instalados y son accesibles en el sistema de la aplicación.  Los detalles de los serializadores instalados se definen mediante la configuración del registro.  Los serializadores de complemento se pueden agregar al registro mediante el <xref:System.Windows.Documents.Serialization.SerializerProvider.RegisterSerializer%2A> método; o si [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] aún no está instalado, el script de instalación de un complemento puede tener directamente conjuntos del registro valores propio.  El <xref:System.Windows.Documents.Serialization.SerializerProvider.UnregisterSerializer%2A> método se puede utilizar para quitar instalado previamente un complemento, o la configuración del registro se puede restablecer de forma similar por una secuencia de comandos de desinstalación.  
  
### <a name="creating-a-plug-in-serializer"></a>Crear un serializador de complemento  
 Tanto los serializadores de complemento como los serializadores vinculados utilizan los mismos métodos y eventos públicos expuestos y, de forma similar, se pueden diseñar para funcionar de forma sincrónica o asincrónica.  Existen tres pasos básicos que se suelen seguir para crear un serializador de complemento:  
  
1.  Implementar y depurar el serializador en primer lugar como serializador vinculado.  Crear inicialmente el serializador compilado y vinculado directamente en una aplicación de prueba proporciona acceso total a los puntos de interrupción y otros servicios de depuración útiles para realizar pruebas.  
  
2.  Después de que el serializador está probado completamente, un <xref:System.Windows.Documents.Serialization.ISerializerFactory> interfaz se agrega al crear un complemento.  El <xref:System.Windows.Documents.Serialization.ISerializerFactory> interfaz permite el acceso completo a todos los [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] objetos que incluye el árbol lógico, <xref:System.Windows.UIElement> objetos, <xref:System.Windows.Documents.IDocumentPaginatorSource>, y <xref:System.Windows.Media.Visual> elementos.  Además <xref:System.Windows.Documents.Serialization.ISerializerFactory> proporciona los mismos métodos sincrónicos y asincrónicos y eventos utilizados por los serializadores vinculados.  Dado que los documentos de gran tamaño pueden tardar tiempo en generarse, se recomiendan las operaciones asincrónicas para mantener una interacción receptiva con el usuario y ofrecer la opción "Cancelar" si se produce algún problema con el almacén de datos.  
  
3.  Después de crear el serializador del complemento, se implementa un script de instalación para distribuir e instalar (y desinstalar) el complemento (véase más arriba, "[Instalar serializadores de complemento](#InstallingPluginSerializers)").  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Documents.Serialization>  
 <xref:System.Windows.Xps.XpsDocumentWriter>  
 <xref:System.Windows.Xps.Packaging.XpsDocument>  
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [XML Paper Specification (XPS): Overview](http://go.microsoft.com/fwlink?LinkID=106246) (XML Paper Specification (XPS): Información general)
