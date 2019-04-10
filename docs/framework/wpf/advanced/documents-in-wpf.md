---
title: Documentos en WPF
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
ms.openlocfilehash: b4057f54934fb5c7c9bb3d4fb97fe8e197e324ad
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59313962"
---
# <a name="documents-in-wpf"></a>Documentos en WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ofrece una amplia gama de características de documento que permiten la creación de contenido de alta fidelidad que está diseñado para ser más accesible y fácil de leer que en generaciones anteriores de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]. Además de las capacidades y la calidad mejoradas, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también proporciona servicios integrados de presentación, empaquetado y seguridad de documentos. En este tema se proporciona una introducción a los tipos de documentos y el empaquetado de documentos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="types_of_documents"></a>   
## <a name="types-of-documents"></a>Tipos de documentos  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] documentos se divide en dos categorías amplias según su uso previsto; Estas categorías de documentos se denominan "documentos fijos" y "documentos dinámicos".  
  
 Los documentos fijos están diseñados para aplicaciones que requieren una presentación precisa de [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)], independiente del hardware de pantalla o de impresora utilizado. Entre los usos típicos de los documentos fijos se incluyen la publicación de escritorio, el procesamiento de textos y el diseño de formularios, donde es fundamental no apartarse del diseño de página original. Como parte de su diseño, un documento fijo mantiene la colocación posicional precisa de los elementos de contenido, independientemente de la pantalla o el dispositivo de impresión en uso. Por ejemplo, una página de un documento fijo que se vea en una pantalla de 96 ppp, aparecerá exactamente igual cuando se imprima en una impresora láser de 600 ppp o en un fotocomponedor de 4800 ppp. El diseño de página sigue siendo el mismo en todos los casos, mientras que la calidad del documento se maximiza según las capacidades de cada dispositivo.  
  
 En comparación, los documentos dinámicos están diseñados para optimizar su presentación y legibilidad, y son óptimos para su uso cuando la facilidad de lectura es el escenario de consumo principal del documento. En lugar de establecer un diseño predefinido, los documentos dinámicos ajustan y redistribuyen dinámicamente su contenido basándose en variables en tiempo de ejecución, como el tamaño de la ventana, la resolución del dispositivo y las preferencias opcionales del usuario. Una página web es un ejemplo sencillo de un documento dinámico donde se da formato al contenido de la página de manera dinámica para ajustarse a la ventana actual. Los documentos dinámicos optimizan la experiencia de visualización y lectura para el usuario, según el entorno en tiempo de ejecución. Por ejemplo, el mismo documento dinámico cambiará de formato de manera dinámica para mejorar la legibilidad óptima en una pantalla de 19 pulgadas de alta resolución o en una pantalla de PDA pequeña de 2×3 pulgadas. Además, los documentos dinámicos tienen un número de características integradas, incluida búsqueda, modos de visualización que optimizan la legibilidad y la capacidad de cambiar el tamaño y el aspecto de las fuentes.  Consulte [Información general sobre documentos dinámicos](flow-document-overview.md) para ver ilustraciones, ejemplos e información detallada sobre los documentos dinámicos.  
  
<a name="document_viewer"></a>   
## <a name="document-controls-and-text-layout"></a>Controles de documentos y diseño del texto  
 .NET Framework proporciona un conjunto de controles previamente compilados que simplifican el uso de documentos fijos, los documentos dinámicos y el texto general dentro de la aplicación.  La presentación de contenido de documentos fijos es compatible con la <xref:System.Windows.Controls.DocumentViewer> control.  Tres controles diferentes admiten la presentación del contenido del documento dinámico: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, y <xref:System.Windows.Controls.FlowDocumentScrollViewer> que se asignan a distintos escenarios de usuario (consulte las secciones siguientes).  Otros controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporcionan un diseño simplificado para admitir los usos de texto generales (consulte [Texto en la interfaz de usuario](#text_in_the_user_interface) más adelante).  
  
### <a name="fixed-document-control---documentviewer"></a>Control de documentos fijos: DocumentViewer  
 El <xref:System.Windows.Controls.DocumentViewer> control está diseñado para mostrar <xref:System.Windows.Documents.FixedDocument> contenido. El <xref:System.Windows.Controls.DocumentViewer> control proporciona una interfaz de usuario intuitiva que proporciona compatibilidad integrada para operaciones comunes, incluida la salida impresa, copiar al Portapapeles, zoom y las características de búsqueda de texto. El control proporciona acceso a las páginas de contenido a través de un mecanismo de desplazamiento conocido. Al igual que todos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controles, <xref:System.Windows.Controls.DocumentViewer> admite tener completas o parciales, lo que permite el control visualmente integrarse en prácticamente cualquier aplicación o entorno.  
  
 <xref:System.Windows.Controls.DocumentViewer> está diseñado para mostrar el contenido de un modo de solo lectura; la edición o modificación de contenido no está disponible y no se admite.  
  
<a name="flow_document"></a>   
### <a name="flow-document-controls"></a>Controles de documentos dinámicos  
 **Nota:** Para obtener más información sobre las características de documento de flujo y cómo crearlos, vea [Flow Document Overview](flow-document-overview.md).  
  
 Tres controles admiten la presentación del contenido del documento dinámico: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, y <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
#### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> incluye características que permiten al usuario elegir dinámicamente entre distintos modos de visualización, incluido un modo de vista de página única (una página a la vez), dos página a la vez (formato de lectura de libro) modo y un modo de desplazamiento continuo (sin límite) de visualización.  Para obtener más información acerca de estos modos de visualización, consulte <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  Si no tiene la capacidad de cambiar dinámicamente entre distintos modos de visualización, <xref:System.Windows.Controls.FlowDocumentPageViewer> y <xref:System.Windows.Controls.FlowDocumentScrollViewer> proporcionan dinámico más ligeros visores de contenido que se han corregido en un modo de visualización concreto.  
  
#### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer y FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> Muestra el contenido en la página en tiempo de modo de vista, mientras <xref:System.Windows.Controls.FlowDocumentScrollViewer> muestra el contenido en modo de desplazamiento continuo.  Ambos <xref:System.Windows.Controls.FlowDocumentPageViewer> y <xref:System.Windows.Controls.FlowDocumentScrollViewer> son fijos para un modo de visualización concreto. Comparar con <xref:System.Windows.Controls.FlowDocumentReader>, que incluye características que permiten al usuario elegir dinámicamente entre distintos modos de visualización (tal como lo proporciona el <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> enumeración), a costa de recursos más intensiva que <xref:System.Windows.Controls.FlowDocumentPageViewer> o <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 De manera predeterminada, siempre se muestra una barra de desplazamiento vertical y una barra de desplazamiento horizontal se vuelve visible cuando es necesario. El valor predeterminado [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para <xref:System.Windows.Controls.FlowDocumentScrollViewer> no incluye una barra de herramientas; sin embargo, el <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> propiedad puede utilizarse para habilitar una barra de herramientas integrada.  
  
<a name="text_in_the_user_interface"></a>   
### <a name="text-in-the-user-interface"></a>Texto en la interfaz de usuario  
 Además de agregar texto a documentos, el texto, obviamente, puede usarse en la UI de una aplicación, como en formularios. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye varios controles para dibujar texto en la pantalla. Cada control se destina a un escenario diferente y tiene su propia lista de características y limitaciones. En general, el <xref:System.Windows.Controls.TextBlock> elemento se debe usar cuando se requiere, como una frase breve en compatibilidad con texto limitado un [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> se puede usar cuando se requiere la compatibilidad de texto mínima. Para obtener más información, consulte [Información general sobre TextBlock](../controls/textblock-overview.md).  
  
<a name="packaging"></a>   
## <a name="document-packaging"></a>Empaquetado de documentos  
 El <xref:System.IO.Packaging> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] proporcionan un medio eficaz para organizar los datos de la aplicación, contenido del documento y los recursos relacionados en un contenedor único de fácil acceso, portátil y fácil de distribuir. Un archivo ZIP es un ejemplo de un <xref:System.IO.Packaging.Package> tipo capaz de contener varios objetos como una sola unidad. El empaquetado [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] proporcionar un valor predeterminado <xref:System.IO.Packaging.ZipPackage> implementación diseñado con un estándar de convenciones de empaquetado abierto con arquitectura de archivos XML y ZIP. Las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de empaquetado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] facilitan la creación de paquetes, así como el almacenamiento y el acceso a objetos dentro de ellos. Un objeto almacenado en un <xref:System.IO.Packaging.Package> se conoce como un <xref:System.IO.Packaging.PackagePart> ("elemento"). Los paquetes también pueden incluir certificados digitales firmados que pueden utilizarse para identificar al originador de un elemento y para validar que no se ha modificado el contenido de un paquete.  Los paquetes también incluyen un <xref:System.IO.Packaging.PackageRelationship> característica que permite obtener información adicional va a agregar a un paquete o asociarla con elementos concretos sin modificar el contenido de los elementos existentes.  Los servicios de paquetes también admiten [!INCLUDE[TLA#tla_rm](../../../../includes/tlasharptla-rm-md.md)].  
  
 La arquitectura de paquetes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sirve como base para varias tecnologías clave:  
  
-   [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] documentos que cumplen el [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)].  
  
-   Documentos XML de formato abierto (.docx) de Microsoft Office "12".  
  
-   Formatos de almacenamiento personalizados para su propio diseño de aplicaciones.  
  
 Según el empaquetado de las API, un <xref:System.Windows.Xps.Packaging.XpsDocument> está diseñado específicamente para almacenar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] documentos de contenido fijo. Un <xref:System.Windows.Xps.Packaging.XpsDocument> es un documento independiente que se puede abrir en un visor, se muestran en un <xref:System.Windows.Controls.DocumentViewer> control enrutar a una cola de impresión, o imprime directamente en un [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-impresora compatible.  
  
 Las secciones siguientes proporcionan información adicional sobre el <xref:System.IO.Packaging.Package> y <xref:System.Windows.Xps.Packaging.XpsDocument> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] proporcionado con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="packages"></a>   
### <a name="package-components"></a>Componentes de paquetes  
 Las API de empaquetado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permiten organizar los datos de aplicación y documentos en una sola unidad portátil. Un archivo ZIP es uno de los tipos más comunes de paquetes y es el tipo de paquete predeterminado que se proporciona con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  <xref:System.IO.Packaging.Package> es una clase abstracta desde la que <xref:System.IO.Packaging.ZipPackage> se implementa mediante un estándar XML y ZIP archivo arquitectura abierta.  El <xref:System.IO.Packaging.Package.Open%2A> usos del método <xref:System.IO.Packaging.ZipPackage> para crear y usar archivos ZIP de forma predeterminada. Un paquete puede contener tres tipos básicos de elementos:  
  
|||  
|-|-|  
|<xref:System.IO.Packaging.PackagePart>|Archivos de contenido, datos, documentos y recursos de la aplicación.|  
|<xref:System.IO.Packaging.PackageDigitalSignature>|[Certificado X.509] para la identificación, autenticación y validación.|  
|<xref:System.IO.Packaging.PackageRelationship>|Información agregada relacionada con el paquete o un elemento concreto.|  
  
<a name="PackageParts"></a>   
#### <a name="packageparts"></a>PackageParts  
 Un <xref:System.IO.Packaging.PackagePart> ("elemento") es una clase abstracta que hace referencia a un objeto almacenado en un <xref:System.IO.Packaging.Package>. En un archivo ZIP, los elementos del paquete corresponden a los archivos individuales almacenados en el archivo ZIP.  <xref:System.IO.Packaging.ZipPackagePart> proporciona la implementación predeterminada para los objetos serializables almacenados en un <xref:System.IO.Packaging.ZipPackage>.  Al igual que un sistema de archivos, los elementos incluidos en el paquete se almacenan en directorios jerárquicos o en una organización de "estilo de carpetas".  Mediante el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] empaquetar las API, las aplicaciones pueden escribir, almacenar y leer varios <xref:System.IO.Packaging.PackagePart> objetos con un único contenedor de archivos ZIP.  
  
<a name="PackageDigitalSignatures"></a>   
#### <a name="packagedigitalsignatures"></a>PackageDigitalSignatures  
 Para la seguridad, un <xref:System.IO.Packaging.PackageDigitalSignature> ("firma digital") se puede asociar con los elementos dentro de un paquete. Un <xref:System.IO.Packaging.PackageDigitalSignature> incorpora [509] que proporciona dos características:  
  
1. Identifica y autentica al originador del elemento.  
  
2. Valida que no se haya modificado el elemento.  
  
 La firma digital no impide que se modifique un elemento, pero no se podrá realizar la comprobación de validación de la firma digital si el elemento se ha modificado de alguna manera. La aplicación, a continuación, puede emprender la acciones apropiadas: por ejemplo, bloquear la apertura del elemento o notificar al usuario que se ha modificado el elemento y que los datos no son seguros.  
  
<a name="PackageRelationships"></a>   
#### <a name="packagerelationships"></a>PackageRelationships  
 Un <xref:System.IO.Packaging.PackageRelationship> ("relación") proporciona un mecanismo para asociar información adicional con el paquete o un elemento dentro del paquete. Una relación es una función de nivel del paquete que puede asociar información adicional a un elemento sin modificar el contenido real del elemento. Insertar directamente nuevos datos en el contenido del elemento no suele ser práctico en muchos casos:  
  
-   No se conocen el tipo real del elemento ni su esquema de contenido.  
  
-   Incluso si se conocen, el esquema de contenido podría no proporcionar un medio para agregar nueva información.  
  
-   El elemento puede estar firmado digitalmente o cifrado, impidiendo cualquier modificación.  
  
 Las relaciones de los paquetes proporcionan un medio reconocible para agregar y asociar información adicional a los elementos individuales o al paquete completo. Las relaciones de los paquetes se utilizan para dos funciones principales:  
  
1. Definir las relaciones de dependencia de un elemento con otro elemento.  
  
2. Definir las relaciones de información que agregan notas u otros datos relacionados con el elemento.  
  
 Un <xref:System.IO.Packaging.PackageRelationship> proporciona un medio rápido y reconocible para definir las dependencias y agregar otra información asociada con una parte del paquete o el paquete como un todo.  
  
<a name="Dependency_Relationships"></a>   
##### <a name="dependency-relationships"></a>Relaciones de dependencia  
 Las relaciones de dependencia se utilizan para describir las dependencias que mantiene un elemento con otros elementos. Por ejemplo, un paquete puede contener un elemento HTML que incluya una o más etiquetas de imagen \<img>. Las etiquetas de imagen hacen referencia a imágenes que se encuentran en otros elementos internos del paquete o externos al paquete (por ejemplo, a los que se pueda acceder a través de Internet). Creación de un <xref:System.IO.Packaging.PackageRelationship> asociado con el archivo HTML permite detectar y tener acceso a los recursos dependientes rápidos y sencillo. Una aplicación de explorador o de visor puede tener acceso directamente a las relaciones entre los elementos y comenzar a ensamblar de inmediato los recursos dependientes sin conocer el esquema ni analizar el documento.  
  
<a name="Information_Relationships"></a>   
##### <a name="information-relationships"></a>Relaciones de información  
 Similar a una nota o anotación, un <xref:System.IO.Packaging.PackageRelationship> también se puede usar para almacenar otros tipos de información que se asociará con un elemento sin tener que modificar el contenido del mismo.  
  
<a name="XPS_Documents"></a>   
## <a name="xps-documents"></a>Documentos XPS  
 [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] documento es un paquete que contiene uno o más documentos fijos junto con todos los recursos y la información necesaria para la representación.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] También es nativo [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] formato de archivo de cola de impresión.  Un <xref:System.Windows.Xps.Packaging.XpsDocument> se almacena en el conjunto de datos ZIP estándar y puede incluir una combinación de componentes XML y binarios, como los archivos de imagen y la fuente. Se utilizan [PackageRelationships](#PackageRelationships) para definir las dependencias entre el contenido y los recursos necesarios para representar totalmente el documento.  El <xref:System.Windows.Xps.Packaging.XpsDocument> diseño proporciona una solución de documento único, de alta fidelidad que admita varios usos:  
  
-   Lectura, escritura y almacenamiento de contenido y recursos de documentos fijos como un archivo único portátil y fácil de distribuir.  
  
-   Visualización de documentos con la aplicación Visor de [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
-   Generación de documentos en el formato nativo de salida de cola de impresión de [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)].  
  
-   Enrutamiento de documentos directamente a una impresora compatible con [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
## <a name="see-also"></a>Vea también

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
