---
title: "Información general de la arquitectura de metadatos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: metadata [WCF], overview
ms.assetid: 1d37645e-086d-4d68-a358-f3c5b6e8205e
caps.latest.revision: "24"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1fa7fea1709f2664abe45ebdb916183a46885612
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="metadata-architecture-overview"></a>Información general de la arquitectura de metadatos
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] proporciona una infraestructura enriquecida para exportar, publicar, recuperar e importar metadatos de servicio. Los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usan metadatos para describir cómo interactuar con los extremos del servicio de forma que las herramientas, como Svcutil.exe, puedan generar automáticamente código de cliente para tener acceso al servicio.  
  
 La mayoría de los tipos que constituyen la infraestructura de metadatos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] residen en el espacio de nombres <xref:System.ServiceModel.Description>.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la clase <xref:System.ServiceModel.Description.ServiceEndpoint> para describir los extremos de un servicio. Puede utilizar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para generar metadatos para extremos de servicio o importar metadatos de servicio para generar instancias de <xref:System.ServiceModel.Description.ServiceEndpoint>.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] representa los metadatos de un servicio en forma de una instancia del tipo de <xref:System.ServiceModel.Description.MetadataSet>, cuya estructura está estrechamente ligada al formato de serialización de metadatos definido en WS-MetadataExchange. El tipo <xref:System.ServiceModel.Description.MetadataSet> empaqueta los metadatos de servicio reales, como, por ejemplo, documentos del lenguaje de descripción de servicios Web (WSDL), documentos de esquema XML o expresiones de WS-Policy, como una colección de instancias de <xref:System.ServiceModel.Description.MetadataSection>. Cada instancia de <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType> contiene un dialecto de metadatos y un identificador concretos. <xref:System.ServiceModel.Description.MetadataSection?displayProperty=nameWithType> puede contener los elementos siguientes en su propiedad <xref:System.ServiceModel.Description.MetadataSection.Metadata%2A?displayProperty=nameWithType>:  
  
-   Metadatos sin formato.  
  
-   Instancia de <xref:System.ServiceModel.Description.MetadataReference>.  
  
-   Instancia de <xref:System.ServiceModel.Description.MetadataLocation>.  
  
 Una instancia de <xref:System.ServiceModel.Description.MetadataReference?displayProperty=nameWithType> apunta a otro extremo de intercambio de metadatos (MEX) y las instancias de <xref:System.ServiceModel.Description.MetadataLocation?displayProperty=nameWithType> apuntan a un documento de metadatos mediante una dirección URL HTTP. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite el uso de documentos WSDL para describir extremos de servicio, contratos de servicio, enlaces, patrones de intercambio de mensajes, mensajes y mensajes de error implementados por un servicio. Los tipos de datos utilizados por el servicio se describen en documentos WSDL utilizando el esquema XML. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Importación del esquema y exportar](../../../../docs/framework/wcf/feature-details/schema-import-and-export.md). Puede utilizar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para exportar e importar extensiones WSDL para el comportamiento del servicio, comportamientos del contrato y elementos de enlace que extienden la funcionalidad de un servicio. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Exportación de metadatos personalizados para una extensión de WCF](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md).  
  
## <a name="exporting-service-metadata"></a>Exportación de metadatos de servicios  
 En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], *exportación de metadatos* es el proceso de describir extremos de servicio y proyectarlos en una representación paralela y estandarizada que los clientes pueden utilizar para aprender a usar el servicio. Para exportar metadatos desde instancias de <xref:System.ServiceModel.Description.ServiceEndpoint>, utilice una implementación de la clase abstracta <xref:System.ServiceModel.Description.MetadataExporter>. Una implementación <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> genera metadatos que se encapsulan en una instancia <xref:System.ServiceModel.Description.MetadataSet>.  
  
 La clase <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> proporciona un marco para generar expresiones de directiva que describen las funciones y requisitos de un enlace de extremo y sus operaciones asociadas, mensajes y errores. Estas expresiones de directiva se capturan en una instancia <xref:System.ServiceModel.Description.PolicyConversionContext>. Una implementación <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> puede asociar a continuación estas expresiones de directiva a los metadatos que genera.  
  
 <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> llama en cada <xref:System.ServiceModel.Channels.BindingElement?displayProperty=nameWithType> que implementa la interfaz <xref:System.ServiceModel.Description.IPolicyExportExtension> en el enlace de <xref:System.ServiceModel.Description.ServiceEndpoint> al generar un objeto <xref:System.ServiceModel.Description.PolicyConversionContext> para la implementación <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> que se va a usar. Puede exportar nuevas aserciones de directiva mediante la implementación de la interfaz <xref:System.ServiceModel.Description.IPolicyExportExtension> en sus implementaciones personalizadas del tipo <xref:System.ServiceModel.Channels.BindingElement>.  
  
 El tipo <xref:System.ServiceModel.Description.WsdlExporter> es la implementación de la clase abstracta <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> incluida en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. El tipo <xref:System.ServiceModel.Description.WsdlExporter> genera los metadatos WSDL con expresiones de directiva asociadas.  
  
 Para exportar metadatos WSDL personalizados o extensiones WSDL para los comportamientos del extremo, comportamientos del contrato o elementos de enlace en un extremo de servicio, puede implementar la interfaz <xref:System.ServiceModel.Description.IWsdlExportExtension>. <xref:System.ServiceModel.Description.WsdlExporter> examina una instancia de <xref:System.ServiceModel.Description.ServiceEndpoint> en búsqueda de elementos de enlace, comportamientos de operaciones, comportamientos de contratos y comportamientos de extremos que implementan la interfaz <xref:System.ServiceModel.Description.IWsdlExportExtension> al generar el documento WSDL.  
  
## <a name="publishing-service-metadata"></a>Publicación de metadatos de servicios  
 Los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] publican metadatos mediante la exposición de uno o más extremos de metadatos. La publicación de metadatos de servicios pone a disposición metadatos de servicios mediante protocolos normalizados, como MEX y solicitudes HTTP/GET. Los extremos de metadatos son similares a otros extremos de servicio en cuanto que tienen una dirección, un enlace y un contrato. Puede agregar extremos de metadatos a un host de servicio mediante configuración o código.  
  
 Para publicar extremos de metadatos para un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], debe agregar primero una instancia del comportamiento del servicio <xref:System.ServiceModel.Description.ServiceMetadataBehavior> al servicio. Al agregar una instancia de <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> a su servicio, aumenta su servicio con la capacidad de publicar los metadatos mediante la exposición de uno o más extremos de metadatos. Una vez que agregue el comportamiento del servicio <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>, puede exponer extremos de metadatos que admitan el protocolo MEX o que respondan a solicitudes HTTP/GET.  
  
 Para agregar extremos de metadatos que utilizan el protocolo MEX, agregue extremos de servicio al host de servicio que utilicen el contrato de servicio denominado IMetadataExchange.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] define la <xref:System.ServiceModel.Description.IMetadataExchange> interfaz que tiene este nombre de contrato de servicio. Los extremos de WS-MetadataExchange o los extremos MEX, pueden utilizar uno de los cuatro enlaces predeterminados que los métodos de generador estáticos exponen en la clase <xref:System.ServiceModel.Description.MetadataExchangeBindings> para coincidir con los enlaces predeterminados utilizados por herramientas de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], como Svcutil.exe. También puede configurar extremos de metadatos MEX mediante un enlace personalizado.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> usa un <xref:System.ServiceModel.Description.WsdlExporter?displayProperty=nameWithType> para exportar metadatos para todos los extremos de servicio al servicio. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]exportación de metadatos de un servicio, consulte [exportar e importar metadatos](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
 El <xref:System.ServiceModel.Description.ServiceMetadataBehavior> aumenta su host de servicio agregando una instancia de <xref:System.ServiceModel.Description.ServiceMetadataExtension> como una extensión de su host de servicio. <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> proporciona la implementación para los protocolos de publicación de metadatos. También puede utilizar <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> para obtener los metadatos del servicio en tiempo de ejecución mediante la obtención de acceso a la propiedad <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A>.  
  
> [!CAUTION]
>  Si agrega un extremo MEX en el archivo de configuración de la aplicación y después intenta agregar el objeto <xref:System.ServiceModel.Description.ServiceMetadataBehavior> al host de servicio en el código, obtendrá la excepción siguiente:  
>   
>  System.InvalidOperationException: No se encontró el nombre de contrato 'IMetadataExchange' en la lista de contratos que implementa el servicio Service1. Agregue ServiceMetadataBehavior al archivo de configuración o directamente a ServiceHost para habilitar la compatibilidad para este contrato.  
>   
>  Puede solucionar este problema agregando el <xref:System.ServiceModel.Description.ServiceMetadataBehavior> en el archivo de configuración o agregando el extremo y <xref:System.ServiceModel.Description.ServiceMetadataBehavior> en el código.  
>   
>  Para obtener un ejemplo de cómo agregar <xref:System.ServiceModel.Description.ServiceMetadataBehavior> en un archivo de configuración de aplicación, consulte el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md). Para obtener un ejemplo de cómo agregar <xref:System.ServiceModel.Description.ServiceMetadataBehavior> en el código, vea la [autohospedaje](../../../../docs/framework/wcf/samples/self-host.md) ejemplo.  
  
> [!CAUTION]
>  Cuando se publican metadatos para un servicio que expone dos contratos de servicio distintos, cada uno de los cuales contiene una operación con el mismo nombre, se inicia una excepción. Por ejemplo, si dispone de un servicio que expone un contrato de servicio denominado ICarService que tiene una operación Get(Car c) y el mismo servicio expone un contrato de servicio denominado IBookService que tiene una operación Get(Book b), se inicia una excepción o se muestra un mensaje de error al generar los metadatos del servicio. Para solucionar este problema, realice una de las operaciones siguientes:  
>   
>  -   Cambie el nombre de una de las operaciones.  
> -   Establezca el <xref:System.ServiceModel.OperationContractAttribute.Name%2A> en un nombre distinto.  
> -   Establezca el espacio de nombres de una de las operaciones en un espacio de nombres distinto mediante la propiedad <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
## <a name="retrieving-service-metadata"></a>Recuperación de metadatos de servicios  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede recuperar metadatos de servicio mediante protocolos normalizados como WS-MetadataExchange y HTTP. Ambos protocolos están admitidos por el tipo <xref:System.ServiceModel.Description.MetadataExchangeClient>. Recupera metadatos de servicio utilizando el tipo <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> mediante la proporción de una dirección y un enlace opcional. El enlace utilizado por una instancia de <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> puede ser uno de los enlaces predeterminados de la clase estática <xref:System.ServiceModel.Description.MetadataExchangeBindings>, un enlace proporcionado por el usuario o un enlace cargado desde una configuración de extremo para el contrato `IMetadataExchange`. <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> también puede resolver las referencias a la dirección URL HTTP a los metadatos utilizando el tipo <xref:System.Net.HttpWebRequest>.  
  
 De forma predeterminada, se ata una instancia <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> a una instancia <xref:System.ServiceModel.Channels.ChannelFactoryBase> única. Puede cambiar o reemplazar la instancia <xref:System.ServiceModel.Channels.ChannelFactoryBase> utilizada por <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> invalidando el método virtual <xref:System.ServiceModel.Description.MetadataExchangeClient.GetChannelFactory%2A>. De igual forma, puede cambiar o reemplazar la instancia de <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> utilizada por <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> para realizar solicitudes HTTP/GET mediante la invalidación del método virtual <xref:System.ServiceModel.Description.MetadataExchangeClient.GetWebRequest%2A?displayProperty=nameWithType>.  
  
 Puede recuperar metadatos del servicio mediante solicitudes HTTP/GET o WS-MetadataExchange mediante la herramienta Svcutil.exe y pasando el **/target:metadata** conmutador y una dirección. Svcutil.exe descarga los metadatos en la dirección especificada y guarda los archivos en el disco. Svcutil.exe utiliza una instancia de <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> internamente y carga la configuración de extremo de MEX (desde el archivo de configuración de la aplicación) cuyo nombre coincide con el esquema de la dirección pasada a Svcutil.exe, si existe una. De lo contrario, Svcutil.exe se establece en su valor predeterminado utilizando uno de los enlaces definidos por el tipo de generador estático de <xref:System.ServiceModel.Description.MetadataExchangeBindings>.  
  
## <a name="importing-service-metadata"></a>Importación de metadatos de servicios  
 En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], la importación de metadatos es el proceso que consiste en generar una representación abstracta de un servicio o los componentes de sus metadatos. Por ejemplo, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede importar instancias de<xref:System.ServiceModel.Description.ServiceEndpoint>, instancias de <xref:System.ServiceModel.Channels.Binding> o instancias de <xref:System.ServiceModel.Description.ContractDescription> a partir de un documento WSDL para un servicio. Para importar los metadatos del servicio en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], utilice una implementación de la clase abstracta <xref:System.ServiceModel.Description.MetadataImporter>. Los tipos que derivan de la clase <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> implementan la compatibilidad para la importación de formatos de metadatos que se benefician de la importación lógica de WS-Policy en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Una implementación de <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> recoge las expresiones de directivas asociadas a los metadatos del servicio en un objeto <xref:System.ServiceModel.Description.PolicyConversionContext>. <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> procesa, a continuación, las directivas como parte de la importación de los metadatos llamando a las implementaciones de la interfaz <xref:System.ServiceModel.Description.IPolicyImportExtension> de la propiedad <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A>.  
  
 Puede agregar compatibilidad para la importación de nuevas aserciones de directivas en un <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> agregando su propia implementación de la interfaz <xref:System.ServiceModel.Description.IPolicyImportExtension> a la colección <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A> en una instancia <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType>. De manera alternativa, puede registrar su extensión de importación de directivas en el archivo de configuración de la aplicación cliente.  
  
 El tipo <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> es la implementación de la clase abstracta <xref:System.ServiceModel.Description.MetadataImporter?displayProperty=nameWithType> incluida en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. El tipo <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> importa metadatos del WSDL con directivas adjuntas que se empaquetan en un objeto <xref:System.ServiceModel.Description.MetadataSet>.  
  
 Puede agregar compatibilidad para la importación de extensiones WSDL implementando la interfaz <xref:System.ServiceModel.Description.IWsdlImportExtension> y agregando, a continuación, su implementación a la propiedad <xref:System.ServiceModel.Description.WsdlImporter.WsdlImportExtensions%2A> de su instancia <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>. El <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> también puede cargar implementaciones de la interfaz <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> registrada en el archivo de configuración de la aplicación cliente.  
  
## <a name="dynamic-bindings"></a>Enlaces dinámicos  
 Puede actualizar dinámicamente el enlace que utiliza para crear un canal en un extremo de servicio en caso de que el enlace del extremo cambie o usted desee crear un canal en un extremo que utiliza el mismo contrato pero que tiene un enlace diferente. Puede utilizar la clase estática <xref:System.ServiceModel.Description.MetadataResolver> para recuperar e importar metadatos en tiempo de ejecución para extremos de servicio que implementan un contrato concreto. A continuación, puede utilizar los objetos <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType> importados para crear un cliente o generador de canales en el extremo deseado.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Description>  
 [Formatos de metadatos](../../../../docs/framework/wcf/feature-details/metadata-formats.md)  
 [Exportación e importación de metadatos](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)  
 [Publicación de metadatos](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)  
 [Recuperación de metadatos](../../../../docs/framework/wcf/feature-details/retrieving-metadata.md)  
 [Uso de los metadatos](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [Consideraciones de seguridad con metadatos](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)  
 [Extender el sistema de metadatos](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)
