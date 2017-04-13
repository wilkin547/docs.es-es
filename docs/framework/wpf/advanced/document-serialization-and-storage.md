---
title: "Almacenamiento y serializaci&#243;n de documentos | Microsoft Docs"
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
  - "documentos, serialización"
  - "documentos, storage"
  - "serialización de documentos"
  - "almacenamiento de documentos"
ms.assetid: 4839cd87-e206-4571-803f-0200098ad37b
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Almacenamiento y serializaci&#243;n de documentos
[!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] proporciona un entorno eficaz para crear y mostrar documentos de gran calidad.  Las características mejoradas que admiten tanto documentos fijos como dinámicos y controles de vista avanzados, todo ello combinado con eficaces funciones gráficas 2D y 3D aportan a las aplicaciones [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] un nuevo nivel de calidad y experiencia del usuario.  La posibilidad de administrar con flexibilidad una representación en memoria de un documento es una característica clave de [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]. Por su parte, la capacidad de guardar y cargar con eficacia documentos de un almacén de datos es algo imprescindible en casi todas las aplicaciones.  El proceso de convertir un documento de una representación en memoria interna en un almacén de datos externo se denomina [serialización](GTMT).  El proceso inverso de leer un almacén de datos y volver a crear la instancia en memoria original se denomina deserialización.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="AboutSerialization"></a>   
## Serialización de documentos  
 En una situación ideal, el proceso de [serializar](GTMT) un documento a partir de su representación en memoria y de deserializarlo para volver a crear una instancia de él en memoria resulta transparente a la aplicación.  La aplicación llama a un método serializador de "escritura" para guardar el documento, mientras que un método deserializador de "lectura" obtiene acceso al almacén de datos y vuelve a crear la instancia original en memoria.  Normalmente, la aplicación no tiene que ocuparse del formato concreto en el que se almacenan los datos, siempre que el proceso de serialización y deserialización vuelva a crear el documento en su forma original.  
  
 Con frecuencia, las aplicaciones proporcionan varias opciones de serialización que permiten al usuario guardar documentos en un soporte diferente o con un formato diferente.  Por ejemplo, una aplicación podría ofrecer a opciones de "Guardar como" para almacenar un documento en un archivo de disco, una base de datos o un servicio Web.  De igual modo, diferentes serializadores podrían almacenar el documento en diversos formatos, tales como HTML, RTF, XML, XP o, como alternativa, en un formato de otro fabricante.  Para la aplicación, la serialización define una interfaz que aísla los detalles del soporte de almacenamiento dentro de la implementación de cada serializador concreto.  Además de las ventajas de encapsular los detalles del almacenamiento, las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]<xref:System.Windows.Documents.Serialization> proporcionan otras características importantes.  
  
### Características de los serializadores de documentos de .NET Framework 3.0  
  
-   El acceso directo a los objetos de documento de alto nivel \([árbol lógico](GTMT) y visual\) permite el almacenamiento eficaz de contenido paginado, elementos 2D y 3D, imágenes, multimedia, hipervínculos, anotaciones y otro contenido de compatibilidad.  
  
-   Funcionamiento [sincrónico](GTMT) y [asincrónico](GTMT).  
  
-   Compatibilidad con los serializadores de complemento con funciones mejoradas:  
  
    -   Acceso en todo el sistema para su uso por parte de todas las aplicaciones [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)].  
  
    -   Sencilla capacidad de detectar complementos de aplicaciones.  
  
    -   Implementación, instalación y actualización sencillas de complementos personalizados de otros fabricantes.  
  
    -   Compatibilidad de la interfaz de usuario con la configuración y las opciones personalizadas en tiempo de ejecución.  
  
### Ruta de acceso de impresión de XPS  
 La ruta de acceso de impresión de [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)][!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] proporciona, además, un mecanismo extensible para la escritura de documentos incluida su salida impresa.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] actúa como formato de archivo de documento y, a la vez, es el formato nativo de cola de impresión para [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)].  Los documentos [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] se pueden enviar directamente a las impresoras compatibles con [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)], sin que sea necesario pasarlos a un formato intermedio.  Consulte [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md) para obtener información adicional sobre las opciones y funciones de salida de la ruta de acceso de impresión.  
  
<a name="PluginSerializers"></a>   
## Serializadores de complemento  
 Las API <xref:System.Windows.Documents.Serialization> proporcionan compatibilidad con serializadores de complemento y serializadores vinculados que se instalan por separado con respecto a la aplicación, se enlazan en tiempo de ejecución y permiten el acceso mediante el mecanismo de detección <xref:System.Windows.Documents.Serialization.SerializerProvider>.  Los serializadores de complemento proporcionan ventajas mejoradas de facilidad de implementación y uso en todo el sistema.  Los serializadores vinculados también se pueden implementar para los entornos de [confianza parcial](GTMT) tales como [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)], donde no es posible tener acceso a los serializadores de complemento.  Los serializadores vinculados, que se basan en una implementación derivada de la clase <xref:System.Windows.Documents.Serialization.SerializerWriter>, se compilan y vinculan directamente en la aplicación.  Tanto los serializadores de complemento como los vinculados funcionan a través de métodos y eventos públicos idénticos, lo que facilita el uso de uno o ambos tipos de serializadores en la misma aplicación.  
  
 Los serializadores de complemento ayudan a los programadores de aplicaciones proporcionando extensibilidad a los nuevos diseños de almacenamiento y formatos de archivo sin tener que codificar directamente cada formato potencial en tiempo de compilación.  Los serializadores de complemento también benefician a los programadores de otros fabricantes, al constituir un medio normalizado para implementar, instalar y actualizar complementos accesibles por el sistema para los formatos de archivo personalizados o de propietario.  
  
### Utilizar un serializador de complemento  
 Los serializadores de complemento son de uso sencillo.  La clase <xref:System.Windows.Documents.Serialization.SerializerProvider> enumera un objeto <xref:System.Windows.Documents.Serialization.SerializerDescriptor> para cada complemento instalado en el sistema.  La propiedad <xref:System.Windows.Documents.Serialization.SerializerDescriptor.IsLoadable%2A> filtra los complementos instalados según la configuración actual y comprueba que la aplicación pueda cargar y utilizar el serializador.  <xref:System.Windows.Documents.Serialization.SerializerDescriptor> también proporciona otras propiedades, tales como <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DisplayName%2A> y <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DefaultFileExtension%2A>, que la aplicación puede utilizar para solicitar al usuario la selección de un serializador para un formato de salida disponible.  Se proporciona un serializador de complemento predeterminado para [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] con [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)], que siempre se enumera.  Después de que el usuario selecciona un formato de salida, se utiliza el método <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> para crear una clase <xref:System.Windows.Documents.Serialization.SerializerWriter> para el formato concreto.  A continuación, se puede llamar al método <xref:System.Windows.Documents.Serialization.SerializerWriter>.<xref:System.Windows.Documents.Serialization.SerializerWriter.Write%2A> para generar la secuencia de salida del documento al almacén de datos.  
  
 En el ejemplo siguiente se muestra una aplicación que utiliza el método <xref:System.Windows.Documents.Serialization.SerializerProvider> en una propiedad "PlugInFileFilter".  PlugInFileFilter enumera los complementos instalados y compila una cadena de filtro con las opciones de archivo disponibles para <xref:Microsoft.Win32.SaveFileDialog>.  
  
 [!code-csharp[DocumentSerialize#DocSerializeFileFilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializefilefilter)]  
  
 Una vez seleccionado por el usuario un nombre del archivo de salida, en el ejemplo siguiente se muestra el uso del método <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> para almacenar un documento determinado en un formato especificado.  
  
 [!code-csharp[DocumentSerialize#DocSerializePlugIn](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializeplugin)]  
  
<a name="InstallingPluginSerializers"></a>   
### Instalar serializadores de complemento  
 La clase <xref:System.Windows.Documents.Serialization.SerializerProvider> proporciona la interfaz de aplicaciones de nivel superior para la detección del serializador de complemento y tener acceso a él.  <xref:System.Windows.Documents.Serialization.SerializerProvider> busca y proporciona a la aplicación una lista de los serializadores instalados y accesibles en el sistema.  Las características concretas de los serializadores instalados se definen mediante valores de configuración del Registro.  Los serializadores de complemento se pueden agregar al Registro mediante el método <xref:System.Windows.Documents.Serialization.SerializerProvider.RegisterSerializer%2A>; o bien, si [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] no está instalado aún, el propio script de instalación del complemento puede configurar directamente los valores del Registro.  El método <xref:System.Windows.Documents.Serialization.SerializerProvider.UnregisterSerializer%2A> se puede utilizar para quitar un complemento previamente instalado; si se prefiere, la configuración del Registro se puede restablecer mediante un script de desinstalación.  
  
### Crear un serializador de complemento  
 Tanto los serializadores de complemento como los serializadores vinculados utilizan los mismos métodos y eventos públicos expuestos; de igual modo, pueden diseñarse para funcionar de manera [sincrónica](GTMT) o [asincrónica](GTMT).  Para crear un serializador de complemento se suelen seguir tres pasos básicos:  
  
1.  Implementar y depurar el serializador en primer lugar como serializador vinculado.  Crear inicialmente el serializador compilado y vinculado directamente en una aplicación de prueba proporciona acceso total a los puntos de interrupción y a otros servicios de depuración útiles para la realización de pruebas.  
  
2.  Una vez probado completamente el serializador, se agrega una interfaz <xref:System.Windows.Documents.Serialization.ISerializerFactory> para crear un complemento.  La interfaz <xref:System.Windows.Documents.Serialization.ISerializerFactory> permite el acceso pleno a todos los objetos [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)], lo que incluye el árbol lógico, los objetos <xref:System.Windows.UIElement>, <xref:System.Windows.Documents.IDocumentPaginatorSource> y los elementos <xref:System.Windows.Media.Visual>.  Por añadidura, <xref:System.Windows.Documents.Serialization.ISerializerFactory> proporciona los mismos métodos y eventos sincrónicos y asincrónicos utilizados por los serializadores vinculados.  Puesto que los documentos grandes pueden tardar tiempo en generarse, se recomiendan operaciones asincrónicas para mantener la sensibilidad a las interacciones con el usuario y proporcionar una opción de cancelación si se presenta cualquier problema con el almacén de datos.  
  
3.  Una vez creado el serializador de complemento, se implementa un script de instalación para distribuir e instalar \(y desinstalar\) el complemento \(consulte la sección anterior "[Instalar serializadores de complemento](#InstallingPluginSerializers)"\).  
  
## Vea también  
 <xref:System.Windows.Documents.Serialization>   
 <xref:System.Windows.Xps.XpsDocumentWriter>   
 <xref:System.Windows.Xps.Packaging.XpsDocument>   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [XML Paper Specification: Overview](http://go.microsoft.com/fwlink?LinkID=106246)