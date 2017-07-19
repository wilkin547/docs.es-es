---
title: "Proveedores de transmisi&#243;n por secuencias (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "proveedores de datos de transmisión por secuencias [WCF Data Services]"
  - "Servicios de datos de Microsoft WCF, datos binarios"
  - "Servicios de datos de Microsoft WCF, proveedores"
  - "Servicios de datos de Microsoft WCF, flujos"
ms.assetid: f0978fe4-5f9f-42aa-a5c2-df395d7c9495
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Proveedores de transmisi&#243;n por secuencias (WCF Data Services)
Un servicio de datos puede exponer datos binarios de objetos grandes.  Estos datos binarios pueden representar secuencias de vídeo y audio, imágenes, archivos de documento u otros tipos de medios binarios.  Cuando una entidad del modelo de datos incluye una o más propiedades binarias, el servicio de datos devuelve estos datos binarios codificados en base 64 en la entrada de la fuente de respuesta.  Dado que la carga y la serialización de datos binarios grandes de esta manera pueden afectar al rendimiento, [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] define un mecanismo para recuperar datos binarios independientemente de la entidad a la que pertenezcan.  Para ello, se separan los datos binarios de la entidad en uno o varios flujos de datos.  
  
-   Recurso multimedia: los datos binarios que pertenecen a una entidad, como vídeo, audio, imagen u otro tipo de flujo de recursos multimedia.  
  
-   Entrada de vínculo multimedia: entidad con una referencia a un flujo de recursos multimedia relacionado.  
  
 Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], defina un flujo de recursos binarios implementando un proveedor de transmisión de datos por secuencias.  La implementación del proveedor de transmisión por secuencias proporciona al servicio de datos la secuencia de recursos multimedia asociada con una entidad concreta como objeto <xref:System.IO.Stream>.  Esta implementación permite que el servicio de datos acepte y devuelva los recursos multimedia a través del protocolo HTTP como flujos de datos binarios de un tipo MIME especificado.  
  
 La configuración de un servicio de datos para que admita la transmisión por secuencias de datos binarios requiere los siguientes pasos:  
  
1.  Atribuya una o más entidades del modelo de datos como una entrada de vínculo multimedia.  Estas entidades no deben incluir los datos binarios que se van a transmitir por secuencias.  Las propiedades binarias de una entidad siempre se devuelven en la entrada como datos binarios codificados en base 64.  
  
2.  Implemente la interfaz T:System.Data.Services.Providers.IDataServiceStreamProvider.  
  
3.  Defina un servicio de datos que implemente la interfaz <xref:System.IServiceProvider>.  El servicio de datos usa la implementación del método <xref:System.IServiceProvider.GetService%2A> para acceder a la implementación del proveedor de transmisión de datos por secuencias.  Este método devuelve la implementación del proveedor de transmisión por secuencias adecuado.  
  
4.  Habilite flujos de mensajes grandes en la configuración de la aplicación web.  
  
5.  Habilite el acceso a los recursos binarios en el servidor o en un origen de datos.  
  
 Los ejemplos de este tema se basan en un servicio de fotografías de transmisión por secuencias de ejemplo, que se describe con todo detalle en la entrada del blog relacionado con la [parte 1 de la implementación de un proveedor de transmisión por secuencias de la serie de proveedores de transmisión por secuencias de servicios de datos](http://go.microsoft.com/fwlink/?LinkID=198989).  El código fuente de este servicio de ejemplo está disponible en la [página de ejemplo del servicio de datos de fotografía de transmisión por secuencias](http://go.microsoft.com/fwlink/?LinkID=198988) de la galería de código de MSDN.  
  
## Definir una entrada de vínculo multimedia en el modelo de datos  
 El proveedor del origen de datos determina cómo se define una entidad como entrada de vínculo multimedia en el modelo de datos.  
  
 **Proveedor de Entity Framework**  
 Para indicar que una entidad es una entrada de vínculo multimedia, agregue el atributo `HasStream` a la definición del tipo de entidad en el modelo conceptual, como en el siguiente ejemplo:  
  
 [!code-xml[Astoria Photo Streaming Service#HasStream](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria photo streaming service/xml/photodata.edmx#hasstream)]  
  
 También debe agregar el espacio de nombres `xmlns:m=http://schemas.microsoft.com/ado/2007/08/dataservices/metadata` a la entidad o a la raíz del archivo .edmx o del archivo .csdl que definen el modelo de datos.  
  
 [!INCLUDE[crexample](../../../../includes/crexample-md.md)] servicio de datos que usa el proveedor [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] y expone un recurso multimedia, vea la entrada del blog relacionado con la [parte 1 de la implementación de un proveedor de transmisión por secuencias de la serie de proveedores de transmisión por secuencias de servicios de datos](http://go.microsoft.com/fwlink/?LinkID=198989).  
  
 **Proveedor de reflexión**  
 Para indicar que una entidad es una entrada de vínculo multimedia, agregue el atributo <xref:System.Data.Services.Common.HasStreamAttribute> a la clase que define el tipo de entidad en el proveedor de reflexión.  
  
 **Proveedor de servicios de datos personalizados**  
 Cuando se usan proveedores de servicios personalizados, implemente la interfaz <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> para definir los metadatos del servicio de datos.  Para obtener más información, consulta [Proveedores de servicios de datos personalizados](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).  Indique que un flujo de recurso binario pertenezca a la clase <xref:System.Data.Services.Providers.ResourceType> estableciendo el valor de la propiedad <xref:System.Data.Services.Providers.ResourceType.IsMediaLinkEntry%2A> en `true` en la clase <xref:System.Data.Services.Providers.ResourceType> que representa el tipo de entidad, que es una entrada de vínculo multimedia.  
  
## Implementar la interfaz IDataServiceStreamProvider  
 Para crear un servicio de datos que admita flujos de datos binarios, debe implementar la interfaz <xref:System.Data.Services.Providers.IDataServiceStreamProvider>.  Esta implementación habilita el servicio de datos para devolver al cliente datos binarios como flujo y utilizar los datos binarios como flujo enviado desde el cliente.  El servicio de datos crea una instancia de esta interfaz cuando sea necesario para acceder a los datos binarios como flujo.  La interfaz <xref:System.Data.Services.Providers.IDataServiceStreamProvider> especifica los siguientes miembros:  
  
|Nombre de miembro|Descripción|  
|-----------------------|-----------------|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.DeleteStream%2A>|El servicio de datos invoca este método para eliminar el recurso multimedia correspondiente cuando se elimina su entrada de vínculo multimedia.  Cuando se implementa <xref:System.Data.Services.Providers.IDataServiceStreamProvider>, este método contiene el código que elimina el recurso multimedia asociado con la entrada de vínculo multimedia proporcionada.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStream%2A>|El servicio de datos invoca este método para devolver un recurso multimedia como un flujo.  Cuando se implementa <xref:System.Data.Services.Providers.IDataServiceStreamProvider>, este método contiene el código que proporciona un flujo que el servicio de datos utiliza para devolver el recurso multimedia que está asociado a la entrada de vínculo multimedia proporcionada.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStreamUri%2A>|El servicio de datos invoca este método para devolver el URI que se utiliza para solicitar el recurso multimedia de la entrada de vínculo multimedia.  Este valor se usa para crear el atributo `src` en el elemento de contenido de la entrada de vínculo multimedia que se utiliza para solicitar el flujo de datos.  Cuando este método devuelve `null`, el servicio de datos automáticamente determina el URI.  Use este método cuando deba proporcionar clientes con acceso directo a datos binarios sin usar el proveedor de flujos.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetStreamContentType%2A>|El servicio de datos invoca este método para devolver el valor Content\-Type del recurso multimedia asociado con la entrada de vínculo multimedia especificada.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetStreamETag%2A>|El servicio de datos invoca este método para devolver el objeto eTag del flujo de datos que está asociado con la entidad especificada.  Este método se utiliza cuando se administra la simultaneidad de los datos binarios.  Cuando este método devuelve null, el servicio de datos no realiza el seguimiento de la simultaneidad.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A>|El servicio de datos invoca este método para obtener el flujo que se utiliza cuando se recibe el flujo enviado desde el cliente.  Cuando implemente la interfaz <xref:System.Data.Services.Providers.IDataServiceStreamProvider>, debe devolver un flujo grabable en el que el servicio de datos pueda escribir los datos del flujo recibidos.|  
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.ResolveType%2A>|Devuelve un nombre de tipo calificado con el espacio de nombres que representa el tipo que el motor en tiempo de ejecución del servicio de datos debe crear para la entrada de vínculo multimedia asociada al flujo de datos del recurso multimedia que se está insertando.|  
  
## Crear el servicio de transmisión de datos por secuencias  
 Para proporcionar al motor de tiempo de ejecución de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] acceso a la implementación de la interfaz <xref:System.Data.Services.Providers.IDataServiceStreamProvider>, el servicio de datos que cree también debe implementar la interfaz <xref:System.IServiceProvider>.  En el siguiente ejemplo se muestra cómo implementar el método <xref:System.IServiceProvider.GetService%2A> para devolver una instancia de la clase `PhotoServiceStreamProvider` que implemente la interfaz <xref:System.Data.Services.Providers.IDataServiceStreamProvider>.  
  
 [!code-csharp[Astoria Photo Streaming Service#PhotoServiceStreamingProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria photo streaming service/cs/photodata.svc.cs#photoservicestreamingprovider)]
 [!code-vb[Astoria Photo Streaming Service#PhotoServiceStreamingProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria photo streaming service/vb/photodata.svc.vb#photoservicestreamingprovider)]  
  
 Para obtener información general sobre cómo crear un servicio de datos, vea [Configurar el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
## Habilitar flujos binarios grandes en el entorno de hospedaje  
 Cuando cree un servicio de datos en una aplicación web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], se usa [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para proporcionar la implementación del protocolo HTTP. De forma predeterminada, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] limita el tamaño de los mensajes HTTP a solo 65K bytes.  Para poder transmitir datos binarios grandes por secuencias al servicio de datos y desde él, debe configurar también la aplicación web para habilitar archivos binarios grandes y utilizar secuencias para la transferencia.  Para ello, en el elemento `<configuration />` del archivo Web.config de la aplicación agregue lo siguiente:  
  
  
  
> [!NOTE]
>  Debe usar un modo de transferencia del campo <xref:System.ServiceModel.TransferMode?displayProperty=fullName> para asegurarse de que los datos binarios en los mensajes de solicitud y respuesta se transfieran y que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no los almacene en búfer.  
  
 Para obtener más información, vea [Transferencia de mensajes por secuencias](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md) y [Cuotas de transporte](../../../../docs/framework/wcf/feature-details/transport-quotas.md).  
  
 De forma predeterminada, Internet Information Services \(IIS\) también limita el tamaño de las respuestas a 4 MB.  Para habilitar el servicio de datos con el fin de recibir flujos mayores que 4 MB cuando se ejecute en IIS, también debe establecer el atributo `maxRequestLength` del elemento [Elemento httpRuntime \(Esquema de configuración de ASP.NET\)](http://msdn.microsoft.com/es-es/e9b81350-8aaf-47cc-9843-5f7d0c59f369) de la sección de configuración de `<system.web />` como se muestra en el siguiente ejemplo:  
  
  
  
## Usar flujos de datos en una aplicación cliente  
 La biblioteca cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] le permite recuperar y actualizar estos recursos expuestos como flujos binarios en el cliente.  Para obtener más información, consulta [Trabajar con datos binarios](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md).  
  
## Consideraciones para trabajar con un proveedor de transmisión por secuencias  
 A continuación se enumeran algunas de las consideraciones que debe tener en cuenta al implementar un proveedor de transmisiones por secuencias y al tener acceso a los recursos multimedia de un servicio de datos.  
  
-   Los recursos multimedia no admiten solicitudes MERGE.  Utilice una solicitud PUT para cambiar el recurso multimedia de una entidad existente.  
  
-   Una solicitud POST no se puede utilizar para crear una entrada de vínculo multimedia.  En su lugar, debe emitir una solicitud POST para crear un nuevo recurso multimedia y el servicio de datos creará una entrada de vínculo multimedia con los valores predeterminados.  Una solicitud MERGE o PUT posterior puede actualizar esta nueva entidad.  También puede considerar la opción de almacenar en memoria caché la entidad y realizar actualizaciones en el contenedor de elementos eliminados, como establecer el valor de propiedad en el valor del encabezado Slug en la solicitud POST.  
  
-   Cuando se recibe una solicitud POST, el servicio de datos llama a <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> para crear el recurso multimedia antes de llamar a <xref:System.Data.Services.IUpdatable.SaveChanges%2A> para crear la entrada de vínculo multimedia.  
  
-   Una implementación de <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> no debe devolver un objeto <xref:System.IO.MemoryStream>.  Cuando se utiliza este tipo de flujo, se producirán problemas de recursos de memoria cuando el servicio reciba flujos de datos muy grandes.  
  
-   A continuación se enumeran algunas de las consideraciones que debe tener en cuenta al almacenar recursos multimedia en una base de datos:  
  
    -   En el modelo de datos no debe incluirse una propiedad binaria que sea un recurso multimedia.  Todas las propiedades expuestas en un modelo de datos se devuelven en la entrada de una fuente de respuesta.  
  
    -   Para mejorar el rendimiento con un flujo binario grande, recomendamos crear una clase de flujo personalizado para almacenar datos binarios en la base de datos.  La implementación de <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> devuelve esta clase y envía los datos binarios a la base de datos en fragmentos.  En el caso de una base de datos de [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], se recomienda usar un objeto FILESTREAM para transmitir los datos por secuencias a la base de datos cuando los datos binarios ocupen más de 1 MB.  
  
    -   Asegúrese de que la base de datos esté diseñada para almacenar los flujos binarios grandes que vaya a recibir el servicio de datos.  
  
    -   Cuando un cliente envía a una solicitud POST para insertar una entrada de vínculo multimedia con un recurso multimedia en una solicitud única, se llama a <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> para obtener el flujo antes de que el servicio de datos inserte la nueva entidad en la base de datos.  Una implementación del proveedor de transmisiones por secuencias debe ser capaz de controlar este comportamiento del servicio de datos.  Considere la opción de usar una tabla de datos independiente para almacenar los datos binarios o almacenar el flujo de datos en un archivo hasta que la entidad se haya insertado en la base de datos.  
  
-   Cuando implemente los métodos <xref:System.Data.Services.Providers.IDataServiceStreamProvider.DeleteStream%2A>, <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> o <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStream%2A>, debe utilizar el objeto eTag y los valores Content\-Type y que se proporcionan como parámetros de método.  No establezca el objeto eTag ni los encabezados Content\-Type en la implementación del proveedor <xref:System.Data.Services.Providers.IDataServiceStreamProvider>.  
  
-   De forma predeterminada, el cliente envía secuencias binarias grandes mediante codificación de transferencia HTTP fragmentada.  Dado que el servicio de desarrollo de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] no admite este tipo de codificación, no podrá usar este servidor web para hospedar los servicios de transmisión de datos por secuencias que deban aceptar flujos binarios grandes. Para obtener más información sobre el servidor de desarrollo de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], vea [Servidores web en Visual Studio para proyectos web ASP.NET](http://msdn.microsoft.com/es-es/31d4f588-df59-4b7e-b9ea-e1f2dd204328).  
  
<a name="versioning"></a>   
## Requisitos de control de versiones  
 El proveedor de transmisión por secuencias tiene los siguientes requisitos de control de versiones de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]:  
  
-   El proveedor de transmisión por secuencias requiere que el servicio de datos admita la versión 2.0 del protocolo de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] y versiones posteriores.  
  
 Para obtener más información, consulta [Control de versiones del servicio de datos](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).  
  
## Vea también  
 [Proveedores de servicios de datos](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)   
 [Proveedores de servicios de datos personalizados](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md)   
 [Trabajar con datos binarios](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md)