---
title: Almacenamiento y serialización de documentos
ms.date: 03/30/2017
helpviewer_keywords:
- 'serialization of documents [WPF], , '
- documents [WPF], storage
- documents [WPF], serialization
ms.assetid: 4839cd87-e206-4571-803f-0200098ad37b
ms.openlocfilehash: 7ddd887eefd67a3300795396dac26e855f30989e
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70254121"
---
# <a name="document-serialization-and-storage"></a>Almacenamiento y serialización de documentos

Microsoft .NET Framework proporciona un entorno eficaz para crear y mostrar documentos de alta calidad.  Las características mejoradas que admiten tanto documentos fijos como documentos dinámicos, los controles de vista avanzada, combinados con capacidades de gráficos 2D y 3D eficaces, .NET Framework aplicaciones a un nuevo nivel de calidad y experiencia del usuario.  La capacidad de administrar de manera flexible una representación en memoria de un documento es una característica clave de .NET Framework, y poder guardar y cargar documentos de un almacén de datos de forma eficaz es una necesidad de casi todas las aplicaciones.  El proceso de convertir un documento de una representación en memoria interna a un almacén de datos externo se denomina “serialización”.  El proceso inverso de leer un almacén de datos y volver a crear la instancia en memoria original se denomina “deserialización”.

<a name="AboutSerialization"></a>

## <a name="about-document-serialization"></a>Acerca de la serialización de documentos

Lo ideal es que el proceso de serialización y deserialización de un documento desde la memoria y de vuelta hacia esta sea transparente para la aplicación.  La aplicación llama a un método serializador de "escritura" para guardar el documento, mientras que un método deserializador de "lectura" obtiene acceso al almacén de datos y vuelve a crear la instancia original en memoria.  En general, la aplicación no se encarga del formato específico en que se almacenan los datos, siempre que el proceso de serialización y deserialización vuelva a crear el documento en su forma original.

Las aplicaciones suelen proporcionar varias opciones de serialización que permiten al usuario guardar documentos en distintos soportes o en un formato diferente.  Por ejemplo, una aplicación podría ofrecer la opción "Guardar como" para almacenar un documento en un archivo de disco, una base de datos o un servicio web.  De forma similar, diferentes serializadores podrían almacenar el documento en formatos diferentes, por ejemplo, HTML, RTF, XML, XPS o, como alternativa, un formato de otro fabricante.  Para la aplicación, la serialización define una interfaz que aísla los detalles del soporte de almacenamiento dentro de la implementación de cada serializador concreto.  Además de las ventajas de encapsular los detalles de almacenamiento, las <xref:System.Windows.Documents.Serialization> API de .NET Framework proporcionan otras características importantes.

### <a name="features-of-net-framework-30-document-serializers"></a>Características de los serializadores de documentos de .NET Framework 3.0

- El acceso directo a los objetos de documento de alto nivel (árbol lógico y elementos visuales) permite el almacenamiento eficiente de contenido paginado, elementos 2D o 3D, imágenes, elementos multimedia, hipervínculos, anotaciones y otro contenido de compatibilidad.

- Funcionamiento sincrónico y asincrónico.

- Compatibilidad con los serializadores de complemento con funciones mejoradas:

  - Acceso en todo el sistema para que lo usen todas las aplicaciones .NET Framework.

  - Capacidad sencilla de detectar complementos de aplicaciones.

  - Implementación, instalación y actualización sencillas de complementos personalizados de terceros.

  - Compatibilidad de interfaz de usuario para opciones y configuración personalizadas en tiempo de ejecución.

### <a name="xps-print-path"></a>Ruta de impresión XPS

La ruta de impresión de Microsoft .NET Framework XPS también proporciona un mecanismo extensible para escribir documentos a través de la salida impresa.  XPS sirve como formato de archivo de documento y es el formato nativo de la cola [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]de impresión para.  Los documentos XPS se pueden enviar directamente a las impresoras compatibles con XPS sin necesidad de realizar la conversión a un formato intermedio.  Consulte la [Información general sobre impresión](printing-overview.md) para obtener información adicional sobre las capacidades y opciones de salida de la ruta de impresión.

<a name="PluginSerializers"></a>

## <a name="plug-in-serializers"></a>Serializadores de complemento

Las <xref:System.Windows.Documents.Serialization> API proporcionan compatibilidad con los serializadores de complemento y los serializadores vinculados que se instalan de forma independiente de la aplicación, se enlazan en tiempo de ejecución y se <xref:System.Windows.Documents.Serialization.SerializerProvider> obtiene acceso a ellos mediante el mecanismo de detección.  Los serializadores de complemento proporcionan ventajas mejoradas de facilidad de implementación y uso en todo el sistema.  Los serializadores vinculados también pueden implementarse para entornos de confianza parcial, como [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)], donde no se tiene acceso a los serializadores de complemento.  Los serializadores vinculados, que se basan en una implementación derivada <xref:System.Windows.Documents.Serialization.SerializerWriter> de la clase, se compilan y vinculan directamente a la aplicación.  Tanto los serializadores de complemento como los serializadores vinculados funcionan mediante métodos y eventos públicos idénticos que facilitan el uso de uno o ambos tipos de serializadores en la misma aplicación.

Los serializadores de complemento ayudan a los desarrolladores de aplicaciones, al proporcionar extensibilidad a nuevos diseños de almacenamiento y formatos de archivo sin tener que programar directamente para cada formato potencial en tiempo de compilación.  Los serializadores de complemento también benefician a los desarrolladores externos, al proporcionar un medio estandarizado para implementar, instalar y actualizar complementos accesibles por el sistema para formatos de archivo personalizados o de propietario.

### <a name="using-a-plug-in-serializer"></a>Usar un serializador de complemento

Los serializadores de complemento son fáciles de usar.  La <xref:System.Windows.Documents.Serialization.SerializerProvider> clase enumera un <xref:System.Windows.Documents.Serialization.SerializerDescriptor> objeto para cada complemento instalado en el sistema.  La <xref:System.Windows.Documents.Serialization.SerializerDescriptor.IsLoadable%2A> propiedad filtra los complementos instalados en función de la configuración actual y comprueba que la aplicación pueda cargar y usar el serializador.  También proporciona otras propiedades, <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DisplayName%2A> como y <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DefaultFileExtension%2A>, que la aplicación puede usar para pedir al usuario que seleccione un serializador para un formato de salida disponible. <xref:System.Windows.Documents.Serialization.SerializerDescriptor>  Un serializador de complemento predeterminado para XPS se proporciona con .NET Framework y siempre se enumera.  Una vez que el usuario selecciona un formato de <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> salida, el método se usa <xref:System.Windows.Documents.Serialization.SerializerWriter> para crear un para el formato específico.  El elemento de lenguaje <xref:System.Windows.Documents.Serialization.SerializerWriter>.<xref:System.Windows.Documents.Serialization.SerializerWriter.Write%2A> a continuación, se puede llamar al método para generar el flujo del documento en el almacén de datos.

En el ejemplo siguiente se muestra una aplicación que utiliza <xref:System.Windows.Documents.Serialization.SerializerProvider> el método en una propiedad "PlugInFileFilter".  PlugInFileFilter enumera los complementos instalados y crea una cadena de filtro con las opciones de archivo disponibles para un <xref:Microsoft.Win32.SaveFileDialog>.

[!code-csharp[DocumentSerialize#DocSerializeFileFilter](~/samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializefilefilter)]

Una vez que el usuario ha seleccionado un nombre de archivo de salida, en el ejemplo siguiente se muestra <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> el uso del método para almacenar un documento determinado en un formato especificado.

[!code-csharp[DocumentSerialize#DocSerializePlugIn](~/samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializeplugin)]

<a name="InstallingPluginSerializers"></a>

### <a name="installing-plug-in-serializers"></a>Instalar serializadores de complemento

La <xref:System.Windows.Documents.Serialization.SerializerProvider> clase proporciona la interfaz de aplicación de nivel superior para la detección y el acceso del serializador de complementos.  <xref:System.Windows.Documents.Serialization.SerializerProvider>busca y proporciona a la aplicación una lista de los serializadores que están instalados y a los que se puede tener acceso en el sistema.  Los detalles de los serializadores instalados se definen mediante la configuración del registro.  Los serializadores de complemento se pueden agregar al registro mediante el <xref:System.Windows.Documents.Serialization.SerializerProvider.RegisterSerializer%2A> método; o bien, si aún no se ha instalado .NET Framework, el script de instalación del complemento puede establecer directamente los valores del registro.  El <xref:System.Windows.Documents.Serialization.SerializerProvider.UnregisterSerializer%2A> método se puede usar para quitar un complemento instalado previamente o la configuración del registro se puede restablecer de forma similar mediante un script de desinstalación.

### <a name="creating-a-plug-in-serializer"></a>Crear un serializador de complemento

Tanto los serializadores de complemento como los serializadores vinculados utilizan los mismos métodos y eventos públicos expuestos y, de forma similar, se pueden diseñar para funcionar de forma sincrónica o asincrónica.  Existen tres pasos básicos que se suelen seguir para crear un serializador de complemento:

1. Implementar y depurar el serializador en primer lugar como serializador vinculado.  Crear inicialmente el serializador compilado y vinculado directamente en una aplicación de prueba proporciona acceso total a los puntos de interrupción y otros servicios de depuración útiles para realizar pruebas.

2. Una vez que el serializador se ha probado <xref:System.Windows.Documents.Serialization.ISerializerFactory> por completo, se agrega una interfaz para crear un complemento.  La <xref:System.Windows.Documents.Serialization.ISerializerFactory> interfaz permite el acceso completo a todos los objetos .NET Framework que incluye el árbol <xref:System.Windows.UIElement> lógico, <xref:System.Windows.Documents.IDocumentPaginatorSource>los objetos <xref:System.Windows.Media.Visual> , y los elementos.  Además <xref:System.Windows.Documents.Serialization.ISerializerFactory> , proporciona los mismos métodos y eventos sincrónicos y asincrónicos usados por los serializadores vinculados.  Dado que los documentos de gran tamaño pueden tardar tiempo en generarse, se recomiendan las operaciones asincrónicas para mantener una interacción receptiva con el usuario y ofrecer la opción "Cancelar" si se produce algún problema con el almacén de datos.

3. Después de crear el serializador del complemento, se implementa un script de instalación para distribuir e instalar (y desinstalar) el complemento (véase más arriba, "[Instalar serializadores de complemento](#InstallingPluginSerializers)").

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Documents.Serialization>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- [Documentos en WPF](documents-in-wpf.md)
- [Información general sobre impresión](printing-overview.md)
- [Especificación de papel XML: Introducción](https://go.microsoft.com/fwlink?LinkID=106246)
