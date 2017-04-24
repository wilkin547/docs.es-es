---
title: "Documentos en WPF | Microsoft Docs"
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
  - "documentos que se pueden ver en el explorador"
  - "documentos, que se pueden ver en el explorador"
  - "documentos, controles"
  - "documentos, empaquetar"
  - "documentos, diseño del texto"
  - "documentos, tipos de"
  - "documentos, XPS"
  - "empaquetar documentos"
  - "XPS (documentos)"
ms.assetid: 6e8db7bc-050a-4070-aa72-bb8c46e87ff8
caps.latest.revision: 36
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 35
---
# Documentos en WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona una gama amplia de características de documentos que permiten la creación de contenido de alta fidelidad diseñado facilitar su acceso y lectura con respecto a las generaciones anteriores de [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)].  Además de las mejoras en las funciones y en la calidad, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona servicios integrados para la presentación, empaquetado y seguridad de los documentos.  En este tema se proporciona una introducción a los tipos y al empaquetado de documentos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
   
  
<a name="types_of_documents"></a>   
## Tipos de documentos  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] divide los documentos en dos categorías generales basándose en su uso previsto; estas categorías de documento se denominan "documentos fijos" y "documentos dinámicos".  
  
 Los documentos fijos están diseñados para las aplicaciones que requieren una presentación [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)] precisa, independiente del hardware de pantalla o de impresora utilizado.  Los usos típicos para los documentos fijos incluyen la creación de publicaciones, el procesamiento de textos y el diseño de formularios, donde es vital que se respete el diseño de página original.  Un documento fijo mantiene la colocación posicional precisa de los elementos de contenido con independencia del dispositivo de pantalla o de impresión utilizado.  Por ejemplo, una página de un documento fijo presentada en una pantalla de 96 ppp aparecerá exactamente igual cuando se imprima en una impresora láser de 600 ppp o en una máquina tipográfica fotográfica de 4800 ppp.  El diseño de la página permanece inalterado en todos los casos, aunque la calidad del documento se maximiza de acuerdo con las funciones de cada dispositivo.  
  
 En comparación, los documentos dinámicos están diseñados para optimizar su presentación y legibilidad y son óptimos para su uso cuando la facilidad de lectura constituye el principal escenario de consumo del documento.  En lugar de establecerse en un diseño predefinido, este tipo de documentos ajusta y recoloca dinámicamente su contenido basándose en variables de tiempo de ejecución, tales como el tamaño de la ventana, la resolución del dispositivo y las preferencias opcionales del usuario.  Una página web constituye un ejemplo sencillo de un documento dinámico donde se da formato al contenido de la página dinámicamente para ajustarlo a la ventana activa.  Los documentos dinámicos optimizan la experiencia de visualización y lectura del usuario, basándose en el entorno de tiempo de ejecución.  Por ejemplo, el mismo documento dinámico cambiará su formato dinámicamente para aportar una legibilidad óptima en una pantalla de 19 pulgadas de alta resolución o en la pequeña pantalla de un PDA de 2 x 3 pulgadas.  Además, los documentos dinámicos tienen varias características integradas que incluyen la búsqueda, modos de presentación que optimizan la legibilidad y la capacidad de cambiar el tamaño y la apariencia de las fuentes.  Consulte [Información general sobre documentos dinámicos](../../../../docs/framework/wpf/advanced/flow-document-overview.md) para obtener ilustraciones, ejemplos e información detallada sobre documentos dinámicos.  
  
<a name="document_viewer"></a>   
## Controles de documentos y diseño del texto  
 [!INCLUDE[TLA2#tla_avalonwinfx](../../../../includes/tla2sharptla-avalonwinfx-md.md)] proporciona un conjunto de controles previamente compilados que simplifican el uso de los documentos fijos, los documentos dinámicos y el texto general dentro de la aplicación.  La presentación de contenido de documentos fijos se admite mediante el control <xref:System.Windows.Controls.DocumentViewer>.  Tres controles diferentes admiten la presentación de contenido de documentos dinámicos: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer> y <xref:System.Windows.Controls.FlowDocumentScrollViewer> que se asignan a distintos escenarios del usuario \(consulte las secciones más adelante\).  Otros controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporcionan diseño simplificado para admitir los usos de texto general \(consulte [Texto en la interfaz de usuario](#text_in_the_user_interface), más adelante\).  
  
### Control de documentos fijos: DocumentViewer  
 El control <xref:System.Windows.Controls.DocumentViewer> está diseñado para mostrar contenido <xref:System.Windows.Documents.FixedDocument>.  El control <xref:System.Windows.Controls.DocumentViewer> proporciona una interfaz de usuario intuitiva que ofrece compatibilidad integrada para las operaciones comunes, tales como las características de salida impresa, copia en el portapapeles, aplicación de zoom o búsqueda de texto.  El control proporciona acceso a las páginas de contenido mediante un mecanismo de desplazamiento conocido.  Al igual que todos los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Controls.DocumentViewer> admite el cambio de estilo completo o parcial, lo que permite integrar el control visualmente en la práctica totalidad de las aplicaciones y los entornos.  
  
 <xref:System.Windows.Controls.DocumentViewer> se ha diseñado para mostrar el contenido en modo de sólo lectura; la edición o modificación de contenido no está disponible y no se admite.  
  
<a name="flow_document"></a>   
### Controles de documentos dinámicos  
 **Nota:** para obtener información más detallada sobre las características de los documentos dinámicos y cómo crearlos, consulte [Información general sobre documentos dinámicos](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
 Tres controles admiten la presentación de contenido en los documentos dinámicos: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer> y <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
#### FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader> dispone de características que permiten al usuario seleccionar dinámicamente distintos modos de visualización, incluido el modo de visualización de una sola página \(una página a la vez\), dos páginas a la vez \(formato de lectura de libro\) y desplazamiento continuo \(sin límite\).  Para obtener más información sobre estos modos de visualización, consulte <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>.  Si no necesita la capacidad de cambiar dinámicamente entre distintos modos de visualización, <xref:System.Windows.Controls.FlowDocumentPageViewer> y <xref:System.Windows.Controls.FlowDocumentScrollViewer> proporcionan visores de contenido dinámico más ligeros que son fijos para un modo de visualización concreto.  
  
#### FlowDocumentPageViewer y FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer> muestra el contenido en el modo de visualización de una sola página, mientras que <xref:System.Windows.Controls.FlowDocumentScrollViewer> muestra el contenido en modo de desplazamiento continuo.  Tanto <xref:System.Windows.Controls.FlowDocumentPageViewer> como <xref:System.Windows.Controls.FlowDocumentScrollViewer> son fijos para un modo de visualización concreto.  Puede compararlos con <xref:System.Windows.Controls.FlowDocumentReader>, que incluye características que permiten al usuario elegir dinámicamente entre varios modos de visualización \(suministrados por la enumeración <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>\), a costa de exigir un uso más intensivo de recursos que <xref:System.Windows.Controls.FlowDocumentPageViewer> o <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 De manera predeterminada, se muestra siempre una barra de desplazamiento vertical y la barra de desplazamiento horizontal se vuelve visible cuando es necesario.  La [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] predeterminada para <xref:System.Windows.Controls.FlowDocumentScrollViewer> no incluye barra de herramientas; sin embargo, se puede utilizar la propiedad <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> para habilitar una barra de herramientas integrada.  
  
<a name="text_in_the_user_interface"></a>   
### Texto en la interfaz de usuario  
 Además de agregar el texto a los documentos, es evidente que el texto se puede utilizar en la interfaz de usuario de la aplicación, como en los formularios, por ejemplo.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye varios controles para dibujar texto en la pantalla.  Cada control se destina a un escenario diferente y tiene su propia lista de características y limitaciones.  En general, el elemento <xref:System.Windows.Controls.TextBlock> se debe usar cuando se necesita una compatibilidad de texto limitada, como una frase breve en una [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  <xref:System.Windows.Controls.Label> se puede usar cuando se necesita una compatibilidad de texto mínima.  Para obtener más información, consulte [Información general sobre TextBlock](../../../../docs/framework/wpf/controls/textblock-overview.md).  
  
<a name="packaging"></a>   
## Empaquetado de documentos  
 Las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de <xref:System.IO.Packaging> proporcionan un medio eficaz de organizar los datos de la aplicación, el contenido de los documentos y los recursos relacionados en un contenedor único de fácil acceso, portátil y sencillo de distribuir.  Un archivo ZIP es un ejemplo de un tipo de <xref:System.IO.Packaging.Package> capaz de contener varios objetos en una sola unidad.  La [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de empaquetado proporciona una implementación de <xref:System.IO.Packaging.ZipPackage> predeterminada diseñada mediante una norma basada en la especificación Open Packaging Conventions \(OPC, o Convenciones de empaquetado abierto\) con arquitectura de archivo XML y ZIP.  Las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de empaquetado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] facilitan la creación de paquetes, así como el almacenamiento y acceso de objetos en su interior.  Un objeto almacenado en un <xref:System.IO.Packaging.Package> se denomina <xref:System.IO.Packaging.PackagePart> \("elemento"\).  Los paquetes también pueden incluir certificados digitales firmados que se pueden utilizar para identificar al originador de un elemento y comprobar que no se haya modificado el contenido de un paquete.  Los paquetes también incluyen una característica <xref:System.IO.Packaging.PackageRelationship> que permite agregar información adicional a un paquete o asociarla con elementos concretos sin que ello modifique el contenido de los elementos existentes.  Los servicios de empaquetado también admiten [!INCLUDE[TLA#tla_rm](../../../../includes/tlasharptla-rm-md.md)].  
  
 La arquitectura de paquetes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] constituye los cimientos de varias tecnologías fundamentales:  
  
-   Documentos [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] que cumplen [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)].  
  
-   Documentos XML de formato abierto \(.docx\) de Microsoft Office "12".  
  
-   Formatos de almacenamiento personalizados para su propio diseño de aplicaciones.  
  
 Basándose en las API de empaquetado, <xref:System.Windows.Xps.Packaging.XpsDocument> está diseñado específicamente para almacenar documentos de contenido fijo de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  <xref:System.Windows.Xps.Packaging.XpsDocument> es un documento autónomo que se puede abrir en un visor, mostrar en un control <xref:System.Windows.Controls.DocumentViewer>, enrutar a una cola de impresión o imprimir directamente en una impresora compatible con [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
 En las secciones siguientes se proporciona información adicional sobre las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] <xref:System.IO.Packaging.Package> y <xref:System.Windows.Xps.Packaging.XpsDocument> que se proporcionan con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="packages"></a>   
### Empaquetar componentes  
 Las API de empaquetado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permiten organizar los datos y documentos de la aplicación en una sola unidad portátil.  Un archivo ZIP es uno de los tipos más comunes de paquetes y constituye el tipo de empaquetado predeterminado proporcionado con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  <xref:System.IO.Packaging.Package> es una clase abstracta desde la que se implementa <xref:System.IO.Packaging.ZipPackage>mediante una arquitectura de archivos XML de norma abierta y ZIP.  De manera predeterminada, el método <xref:System.IO.Packaging.Package.Open%2A> utiliza <xref:System.IO.Packaging.ZipPackage> para crear y utilizar los archivos ZIP.  Un paquete puede contener tres tipos básicos de elementos:  
  
|||  
|-|-|  
|<xref:System.IO.Packaging.PackagePart>|Contenido de aplicaciones, datos, documentos y archivos de recursos.|  
|<xref:System.IO.Packaging.PackageDigitalSignature>|[Certificado X.509](GTMT) para la identificación, autenticación y validación.|  
|<xref:System.IO.Packaging.PackageRelationship>|Información agregada relacionada con el paquete o con un elemento concreto del mismo.|  
  
<a name="PackageParts"></a>   
#### PackageParts  
 Una clase <xref:System.IO.Packaging.PackagePart> \("elemento"\) es una clase abstracta que hace referencia a un objeto que está almacenado en una clase <xref:System.IO.Packaging.Package>.  En un archivo ZIP, los elementos del paquete corresponden a los archivos individuales almacenados dentro del archivo ZIP.  <xref:System.IO.Packaging.ZipPackagePart> proporciona la implementación predeterminada para los objetos serializables almacenados en <xref:System.IO.Packaging.ZipPackage>.  Como en un sistema de archivos, los elementos contenidos en el paquete se almacenan con una organización de directorios jerárquicos o "de carpetas".  Gracias a las API de empaquetado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], las aplicaciones pueden escribir, almacenar y leer varios objetos <xref:System.IO.Packaging.PackagePart> utilizando un solo contenedor de archivos ZIP.  
  
<a name="PackageDigitalSignatures"></a>   
#### PackageDigitalSignatures  
 Para aportar seguridad, es posible asociar <xref:System.IO.Packaging.PackageDigitalSignature> \("firma digital"\) a los elementos de un paquete.  <xref:System.IO.Packaging.PackageDigitalSignature> incorpora un [509](GTMT) que proporciona dos características:  
  
1.  Identifica y autentica al originador del elemento.  
  
2.  Valida que no se haya modificado el elemento.  
  
 La firma digital no evita que se modifique un elemento, pero se produce un error en una comprobación de la validación en la firma digital si el elemento se ha modificado de alguna forma.  La aplicación puede emprender la acción adecuada; por ejemplo, bloquear la apertura del elemento o notificar al usuario que se ha modificado el elemento y ya no es seguro.  
  
<a name="PackageRelationships"></a>   
#### PackageRelationships  
 <xref:System.IO.Packaging.PackageRelationship> \("relación"\) proporciona un mecanismo para asociar información adicional con el paquete o con un elemento del mismo.  Una relación es una facilidad de nivel del paquete que permite asociar información adicional a un elemento sin modificar el propio contenido del elemento.  Insertar nuevos datos directamente en el contenido del elemento no suele ser práctico en muchos casos:  
  
-   No se conoce el tipo real del elemento ni su esquema de contenido.  
  
-   Aunque se conozca, el esquema de contenido podría no proporcionar un medio de agregar la nueva información.  
  
-   El elemento puede estar firmada digitalmente o cifrada, lo que evitaría cualquier modificación.  
  
 Las relaciones de los paquetes proporcionan un medio reconocible de agregar y asociar información adicional a los elementos individuales o al paquete completo.  Las relaciones de los paquetes se utilizan para dos funciones primarias:  
  
1.  Definir las relaciones de dependencia entre un elemento y otro.  
  
2.  Definir las relaciones de información que agregan notas u otros datos relacionadas con el elemento.  
  
 <xref:System.IO.Packaging.PackageRelationship> proporciona un medio rápido y reconocible de definir dependencias y agregar otra información asociada con un elemento del paquete o con el paquete en su conjunto.  
  
<a name="Dependency_Relationships"></a>   
##### Relaciones de dependencia  
 Las relaciones de dependencia se utilizan para describir las dependencias que un elemento establece con otros elementos.  Por ejemplo, un paquete podría contener un elemento HTML que incluya una o más etiquetas de imagen \<img\>.  Las etiquetas de la imagen hacen referencia a las imágenes que se encuentran en otros elementos que pueden estar contenidos en el propio paquete o ser externos a él \(por ejemplo, accesibles a través de Internet\).  La creación de una relación \(<xref:System.IO.Packaging.PackageRelationship>\) asociada al archivo HTML facilita y agiliza la detección de los recursos dependientes y el acceso a ellos.  Una aplicación de explorador o visor puede tener acceso directamente a las relaciones entre los elementos y comenzar inmediatamente a ensamblar los recursos dependientes sin conocer el esquema ni analizar el documento.  
  
<a name="Information_Relationships"></a>   
##### Relaciones de información  
 De modo similar a una nota o anotación, <xref:System.IO.Packaging.PackageRelationship> se puede utilizar también para almacenar otros tipos de información que se asociarán a un elemento sin tener que modificar el propio contenido del mismo.  
  
<a name="XPS_Documents"></a>   
## Documentos XPS  
 Un documento [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] es un paquete que contiene uno o más documentos fijos junto con todos los recursos y la información necesarios para la presentación.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] también es el formato de archivo nativo de cola de impresión de [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)].  <xref:System.Windows.Xps.Packaging.XpsDocument> se almacena en el conjunto de datos ZIP estándar, y puede incluir una combinación de XML y componentes binarios, como imágenes y archivos de fuente. Se utilizan [PackageRelationships](#PackageRelationships) para definir las dependencias entre el contenido y los recursos necesarios para presentar totalmente el documento.  El diseño de <xref:System.Windows.Xps.Packaging.XpsDocument> proporciona una solución de documento único de alta fidelidad que admite varios usos:  
  
-   Lectura, escritura y almacenamiento de contenido y recursos de documentos fijos en un único archivo portátil y fácil de distribuir.  
  
-   Presentación de documentos con la aplicación Visor de [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
-   Generación de documentos en el formato de salida de cola de impresión de [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)].  
  
-   Enrutamiento directo de documentos a las impresoras compatibles con [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)].  
  
## Vea también  
 <xref:System.Windows.Documents.FixedDocument>   
 <xref:System.Windows.Documents.FlowDocument>   
 <xref:System.Windows.Xps.Packaging.XpsDocument>   
 <xref:System.IO.Packaging.ZipPackage>   
 <xref:System.IO.Packaging.ZipPackagePart>   
 <xref:System.IO.Packaging.PackageRelationship>   
 <xref:System.Windows.Controls.DocumentViewer>   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Información general sobre documentos dinámicos](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [Almacenamiento y serialización de documentos](../../../../docs/framework/wpf/advanced/document-serialization-and-storage.md)