---
title: Documentos
ms.date: 03/30/2017
helpviewer_keywords:
- documents [WPF], packaging
- documents [WPF], text layout
- documents [WPF], XPS
- 'XPS documents [WPF], , '
- documents [WPF], controls
- documents [WPF], types of
- documents [WPF], browser-viewable
ms.assetid: 6e8db7bc-050a-4070-aa72-bb8c46e87ff8
ms.openlocfilehash: e88604c42b253b48ee605f42f24fe301e339f74b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174685"
---
# <a name="documents-in-wpf"></a>Documentos en WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]ofrece una amplia gama de características de documentos que permiten la creación de contenido de alta fidelidad que está diseñado para ser más fácilmente accesible y leído que en generaciones anteriores de Windows. Además de las capacidades y la calidad mejoradas, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también proporciona servicios integrados de presentación, empaquetado y seguridad de documentos. En este tema se proporciona una introducción a los tipos de documentos y el empaquetado de documentos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="types_of_documents"></a>
## <a name="types-of-documents"></a>Tipos de documentos  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] divide los documentos en dos categorías amplias según su uso previsto; estas categorías de documentos se denominan "documentos fijos" y "documentos dinámicos".  
  
 Los documentos fijos están diseñados para aplicaciones que requieren una presentación precisa de "lo que ves es lo que obtienes" (WYSIWYG), independientemente del hardware de la pantalla o de la impresora utilizado. Entre los usos típicos de los documentos fijos se incluyen la publicación de escritorio, el procesamiento de textos y el diseño de formularios, donde es fundamental no apartarse del diseño de página original. Como parte de su diseño, un documento fijo mantiene la colocación posicional precisa de los elementos de contenido, independientemente de la pantalla o el dispositivo de impresión en uso. Por ejemplo, una página de un documento fijo que se vea en una pantalla de 96 ppp, aparecerá exactamente igual cuando se imprima en una impresora láser de 600 ppp o en un fotocomponedor de 4800 ppp. El diseño de página sigue siendo el mismo en todos los casos, mientras que la calidad del documento se maximiza según las capacidades de cada dispositivo.  
  
 En comparación, los documentos dinámicos están diseñados para optimizar su presentación y legibilidad, y son óptimos para su uso cuando la facilidad de lectura es el escenario de consumo principal del documento. En lugar de establecer un diseño predefinido, los documentos dinámicos ajustan y redistribuyen dinámicamente su contenido basándose en variables en tiempo de ejecución, como el tamaño de la ventana, la resolución del dispositivo y las preferencias opcionales del usuario. Una página web es un ejemplo sencillo de un documento dinámico donde se da formato al contenido de la página de manera dinámica para ajustarse a la ventana actual. Los documentos dinámicos optimizan la experiencia de visualización y lectura para el usuario, según el entorno en tiempo de ejecución. Por ejemplo, el mismo documento dinámico cambiará de formato de manera dinámica para mejorar la legibilidad óptima en una pantalla de 19 pulgadas de alta resolución o en una pantalla de PDA pequeña de 2×3 pulgadas. Además, los documentos dinámicos tienen varias características integradas, como la búsqueda, los modos de visualización que optimizan la legibilidad, y la capacidad de cambiar el tamaño y el aspecto de las fuentes.  Consulte [Información general sobre documentos dinámicos](flow-document-overview.md) para ver ilustraciones, ejemplos e información detallada sobre los documentos dinámicos.  
  
<a name="document_viewer"></a>
## <a name="document-controls-and-text-layout"></a>Controles de documentos y diseño del texto  
 .NET Framework proporciona un conjunto de controles predefinidos que simplifican el uso de documentos fijos, documentos de flujo y texto general dentro de la aplicación.  La visualización del contenido fijo <xref:System.Windows.Controls.DocumentViewer> del documento se admite mediante el control.  La visualización del contenido del documento <xref:System.Windows.Controls.FlowDocumentReader> <xref:System.Windows.Controls.FlowDocumentPageViewer>de <xref:System.Windows.Controls.FlowDocumentScrollViewer> flujo es compatible con tres controles diferentes: , , y que se asignan a diferentes escenarios de usuario (consulte las secciones siguientes).  Otros controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporcionan un diseño simplificado para admitir los usos de texto generales (consulte [Texto en la interfaz de usuario](#text_in_the_user_interface) más adelante).  
  
### <a name="fixed-document-control---documentviewer"></a>Control de documentos fijos: DocumentViewer  
 El <xref:System.Windows.Controls.DocumentViewer> control está <xref:System.Windows.Documents.FixedDocument> diseñado para mostrar contenido. El <xref:System.Windows.Controls.DocumentViewer> control proporciona una interfaz de usuario intuitiva que proporciona compatibilidad integrada para operaciones comunes, como la salida de impresión, copiar en el portapapeles, zoom y funciones de búsqueda de texto. El control proporciona acceso a las páginas de contenido a través de un mecanismo de desplazamiento conocido. Al [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] igual <xref:System.Windows.Controls.DocumentViewer> que todos los controles, admite el restyling completo o parcial, lo que permite que el control se integre visualmente en prácticamente cualquier aplicación o entorno.  
  
 <xref:System.Windows.Controls.DocumentViewer>está diseñado para mostrar contenido de una manera de solo lectura; edición o modificación de contenido no está disponible y no es compatible.  
  
<a name="flow_document"></a>
### <a name="flow-document-controls"></a>Controles de documentos dinámicos  

> [!NOTE]
> Para obtener información más detallada sobre las características de documento de flujo y cómo crearlas, consulte [Resumen del documento](flow-document-overview.md)de flujo .  
  
 La visualización del contenido del <xref:System.Windows.Controls.FlowDocumentReader>documento <xref:System.Windows.Controls.FlowDocumentPageViewer>de <xref:System.Windows.Controls.FlowDocumentScrollViewer>flujo es compatible con tres controles: , , y .  
  
#### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader>incluye características que permiten al usuario elegir dinámicamente entre varios modos de visualización, incluido un modo de visualización de una sola página (página a la vez), un modo de visualización de dos páginas a la vez (formato de lectura de libros) y un modo de visualización de desplazamiento continuo (sin fondo).  Para obtener más información sobre <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>estos modos de visualización, consulte .  Si no necesita la capacidad de cambiar dinámicamente <xref:System.Windows.Controls.FlowDocumentPageViewer> entre <xref:System.Windows.Controls.FlowDocumentScrollViewer> diferentes modos de visualización y proporcionar visores de contenido de flujo más ligeros que se fijan en un modo de visualización determinado.  
  
#### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer y FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer>muestra el contenido en modo de visualización <xref:System.Windows.Controls.FlowDocumentScrollViewer> de página a página, mientras que muestra el contenido en modo de desplazamiento continuo.  Ambos <xref:System.Windows.Controls.FlowDocumentPageViewer> <xref:System.Windows.Controls.FlowDocumentScrollViewer> y se fijan a un modo de visualización determinado. Comparar <xref:System.Windows.Controls.FlowDocumentReader>con , que incluye características que permiten al usuario elegir dinámicamente <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> entre varios modos de visualización <xref:System.Windows.Controls.FlowDocumentPageViewer> <xref:System.Windows.Controls.FlowDocumentScrollViewer>(según lo proporcionado por la enumeración), a costa de ser más intensivo en recursos que o .  
  
 De manera predeterminada, siempre se muestra una barra de desplazamiento vertical y una barra de desplazamiento horizontal se vuelve visible cuando es necesario. El [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] valor <xref:System.Windows.Controls.FlowDocumentScrollViewer> predeterminado para no incluye una barra de herramientas; sin <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> embargo, la propiedad se puede utilizar para habilitar una barra de herramientas integrada.  
  
<a name="text_in_the_user_interface"></a>
### <a name="text-in-the-user-interface"></a>Texto en la interfaz de usuario  
 Además de agregar texto a documentos, el texto, obviamente, puede usarse en la UI de una aplicación, como en formularios. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye varios controles para dibujar texto en la pantalla. Cada control se destina a un escenario diferente y tiene su propia lista de características y limitaciones. En general, <xref:System.Windows.Controls.TextBlock> el elemento debe utilizarse cuando se requiere compatibilidad [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]limitada con texto, como una breve frase en un archivo . <xref:System.Windows.Controls.Label>se puede utilizar cuando se requiere un soporte de texto mínimo. Para obtener más información, consulte [Información general sobre TextBlock](../controls/textblock-overview.md).  
  
<a name="packaging"></a>
## <a name="document-packaging"></a>Empaquetado de documentos  
 Las <xref:System.IO.Packaging> API proporcionan un medio eficaz para organizar los datos de la aplicación, el contenido del documento y los recursos relacionados en un único contenedor que es fácil de acceder, portátil y fácil de distribuir. Un archivo ZIP es <xref:System.IO.Packaging.Package> un ejemplo de un tipo capaz de contener varios objetos como una sola unidad. Las API de empaquetado <xref:System.IO.Packaging.ZipPackage> proporcionan una implementación predeterminada diseñada mediante un estándar Open Packaging Conventions con arquitectura de archivos XML y ZIP. Las [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API de empaquetado facilitan la creación de paquetes y el almacenamiento y el acceso a objetos dentro de ellos. Un objeto almacenado <xref:System.IO.Packaging.Package> en a <xref:System.IO.Packaging.PackagePart> se conoce como una ("parte"). Los paquetes también pueden incluir certificados digitales firmados que pueden utilizarse para identificar al originador de un elemento y para validar que no se ha modificado el contenido de un paquete.  Los paquetes <xref:System.IO.Packaging.PackageRelationship> también incluyen una característica que permite agregar información adicional a un paquete o asociarse con partes específicas sin modificar realmente el contenido de las piezas existentes.  Los servicios de paquetes también admiten Microsoft Windows Rights Management (RM).  
  
 La arquitectura de paquetes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sirve como base para varias tecnologías clave:  
  
- Documentos XPS conformes a la especificación de papel XML (XPS).  
  
- Documentos XML de formato abierto (.docx) de Microsoft Office "12".  
  
- Formatos de almacenamiento personalizados para su propio diseño de aplicaciones.  
  
 Basado en las API <xref:System.Windows.Xps.Packaging.XpsDocument> de empaquetado, un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] está diseñado específicamente para almacenar documentos de contenido fijo. Un <xref:System.Windows.Xps.Packaging.XpsDocument> documento es independiente que se puede abrir en un <xref:System.Windows.Controls.DocumentViewer> visor, mostrarse en un control, enrutarse a una cola de impresión o enviarse directamente a una impresora compatible con XPS.  
  
 En las secciones siguientes <xref:System.IO.Packaging.Package> <xref:System.Windows.Xps.Packaging.XpsDocument> se proporciona [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]información adicional sobre las API proporcionadas con .  
  
<a name="packages"></a>
### <a name="package-components"></a>Componentes de paquetes  
 Las API de empaquetado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permiten organizar los datos de aplicación y documentos en una sola unidad portátil. Un archivo ZIP es uno de los tipos más comunes de paquetes y es el tipo de paquete predeterminado que se proporciona con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  <xref:System.IO.Packaging.Package>sí mismo es una <xref:System.IO.Packaging.ZipPackage> clase abstracta desde la que se implementa utilizando una arquitectura de archivos XML y ZIP estándar abierta.  El <xref:System.IO.Packaging.Package.Open%2A> método <xref:System.IO.Packaging.ZipPackage> se utiliza para crear y utilizar archivos ZIP de forma predeterminada. Un paquete puede contener tres tipos básicos de elementos:  
  
|||  
|-|-|  
|<xref:System.IO.Packaging.PackagePart>|Archivos de contenido, datos, documentos y recursos de la aplicación.|  
|<xref:System.IO.Packaging.PackageDigitalSignature>|[Certificado X.509] para la identificación, autenticación y validación.|  
|<xref:System.IO.Packaging.PackageRelationship>|Información agregada relacionada con el paquete o un elemento concreto.|  
  
<a name="PackageParts"></a>
#### <a name="packageparts"></a>PackageParts  
 Un <xref:System.IO.Packaging.PackagePart> ("parte") es una clase abstracta que <xref:System.IO.Packaging.Package>hace referencia a un objeto almacenado en un archivo . En un archivo ZIP, los elementos del paquete corresponden a los archivos individuales almacenados en el archivo ZIP.  <xref:System.IO.Packaging.ZipPackagePart>proporciona la implementación predeterminada para <xref:System.IO.Packaging.ZipPackage>los objetos serializables almacenados en un archivo .  Al igual que un sistema de archivos, los elementos incluidos en el paquete se almacenan en directorios jerárquicos o en una organización de "estilo de carpetas".  Con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las API de empaquetado, las aplicaciones <xref:System.IO.Packaging.PackagePart> pueden escribir, almacenar y leer varios objetos mediante un único contenedor de archivos ZIP.  
  
<a name="PackageDigitalSignatures"></a>
#### <a name="packagedigitalsignatures"></a>PackageDigitalSignatures  
 Por seguridad, <xref:System.IO.Packaging.PackageDigitalSignature> se puede asociar una ("firma digital") con piezas dentro de un paquete. A <xref:System.IO.Packaging.PackageDigitalSignature> incorpora un [509] que proporciona dos características:  
  
1. Identifica y autentica al originador del elemento.  
  
2. Valida que no se haya modificado el elemento.  
  
 La firma digital no impide que se modifique un elemento, pero no se podrá realizar la comprobación de validación de la firma digital si el elemento se ha modificado de alguna manera. La aplicación, a continuación, puede emprender la acciones apropiadas: por ejemplo, bloquear la apertura del elemento o notificar al usuario que se ha modificado el elemento y que los datos no son seguros.  
  
<a name="PackageRelationships"></a>
#### <a name="packagerelationships"></a>PackageRelationships  
 Un <xref:System.IO.Packaging.PackageRelationship> ("relación") proporciona un mecanismo para asociar información adicional con el paquete o una parte dentro del paquete. Una relación es una función de nivel del paquete que puede asociar información adicional a un elemento sin modificar el contenido real del elemento. Insertar directamente nuevos datos en el contenido del elemento no suele ser práctico en muchos casos:  
  
- No se conocen el tipo real del elemento ni su esquema de contenido.  
  
- Incluso si se conocen, el esquema de contenido podría no proporcionar un medio para agregar nueva información.  
  
- El elemento puede estar firmado digitalmente o cifrado, impidiendo cualquier modificación.  
  
 Las relaciones de los paquetes proporcionan un medio reconocible para agregar y asociar información adicional a los elementos individuales o al paquete completo. Las relaciones de los paquetes se utilizan para dos funciones principales:  
  
1. Definir las relaciones de dependencia de un elemento con otro elemento.  
  
2. Definir las relaciones de información que agregan notas u otros datos relacionados con el elemento.  
  
 A <xref:System.IO.Packaging.PackageRelationship> proporciona un medio rápido y detectable para definir dependencias y agregar otra información asociada con una parte del paquete o el paquete en su conjunto.  
  
<a name="Dependency_Relationships"></a>
##### <a name="dependency-relationships"></a>Relaciones de dependencia  
 Las relaciones de dependencia se utilizan para describir las dependencias que mantiene un elemento con otros elementos. Por ejemplo, un paquete puede contener un elemento HTML que incluya una o más etiquetas de imagen \<img>. Las etiquetas de imagen hacen referencia a imágenes que se encuentran en otros elementos internos del paquete o externos al paquete (por ejemplo, a los que se pueda acceder a través de Internet). La <xref:System.IO.Packaging.PackageRelationship> creación de un archivo HTML asociado hace que descubrir y acceder a los recursos dependientes sea rápido y fácil. Una aplicación de explorador o de visor puede tener acceso directamente a las relaciones entre los elementos y comenzar a ensamblar de inmediato los recursos dependientes sin conocer el esquema ni analizar el documento.  
  
<a name="Information_Relationships"></a>
##### <a name="information-relationships"></a>Relaciones de información  
 De forma similar a <xref:System.IO.Packaging.PackageRelationship> una nota o anotación, también se puede utilizar a para almacenar otros tipos de información que se asociarán a una pieza sin tener que modificar realmente el propio contenido de la pieza.  
  
<a name="XPS_Documents"></a>
## <a name="xps-documents"></a>Documentos XPS  
 Xml Paper Specification (XPS) document es un paquete que contiene uno o más documentos fijos junto con todos los recursos e información necesarios para la representación.  XPS es también el formato de archivo de cola de impresión nativo de Windows Vista.  An <xref:System.Windows.Xps.Packaging.XpsDocument> se almacena en el conjunto de datos ZIP estándar y puede incluir una combinación de componentes XML y binarios, como archivos de imagen y fuente. Se utilizan [PackageRelationships](#PackageRelationships) para definir las dependencias entre el contenido y los recursos necesarios para representar totalmente el documento.  El <xref:System.Windows.Xps.Packaging.XpsDocument> diseño proporciona una solución de documento única y de alta fidelidad que admite múltiples usos:  
  
- Lectura, escritura y almacenamiento de contenido y recursos de documentos fijos como un archivo único portátil y fácil de distribuir.  
  
- Visualización de documentos con la aplicación XPS Viewer.  
  
- Salida de documentos en el formato de salida de cola de impresión nativa de Windows Vista.  
  
- Enrutamiento de documentos directamente a una impresora compatible con XPS.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Documents.FixedDocument>
- <xref:System.Windows.Documents.FlowDocument>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.IO.Packaging.ZipPackage>
- <xref:System.IO.Packaging.ZipPackagePart>
- <xref:System.IO.Packaging.PackageRelationship>
- <xref:System.Windows.Controls.DocumentViewer>
- [Texto](optimizing-performance-text.md)
- [Información general sobre documentos dinámicos](flow-document-overview.md)
- [Información general sobre impresión](printing-overview.md)
- [Almacenamiento y serialización de documentos](document-serialization-and-storage.md)
