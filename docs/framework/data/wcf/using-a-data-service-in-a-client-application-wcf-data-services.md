---
title: Usar un servicio de datos en una aplicación cliente (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, getting started
ms.assetid: 90872d0c-e989-4490-b3e9-54afb10d33d4
ms.openlocfilehash: 092f073a138a09fc25b96fbddde5b73992056981
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43732253"
---
# <a name="using-a-data-service-in-a-client-application-wcf-data-services"></a>Usar un servicio de datos en una aplicación cliente (Data Services de WCF)
Puede tener acceso a un servicio que expone un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] fuente especificando un URI a un explorador Web. El URI proporciona la dirección de un recurso y los mensajes de solicitud se envían a estas direcciones para obtener acceso o cambiar los datos subyacentes que el recurso representa. El explorador emite un comando GET de HTTP y devuelve el recurso solicitado como una fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Para obtener más información, consulte [acceder al servicio desde un explorador Web](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
 Aunque un explorador web puede ser útil para probar que un servicio de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] devuelve los datos esperados, normalmente el acceso a los servicios de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] de producción que le permiten crear, actualizar y eliminar datos también se realiza mediante código de aplicación o lenguajes de scripts en una página web. En este tema proporciona información general sobre cómo obtener acceso a [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuentes desde una aplicación cliente.  
  
## <a name="accessing-and-changing-data-using-rest-semantics"></a>Obtener acceso y cambiar datos mediante la semántica REST  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] ayuda a garantiza la interoperabilidad entre los servicios que exponen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuentes y las aplicaciones que consumen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuentes de distribución. Las aplicaciones obtener acceso y cambiar datos en un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-servicio basado en mediante el envío de mensajes de solicitud de una acción HTTP concreta y con un URI que direcciona un recurso de entidad en la que debe realizarse la acción. Cuando sea obligatorio proporcionar datos de la entidad, se proporcionan mediante una carga específicamente codificada en el cuerpo del mensaje.  
  
### <a name="http-actions"></a>Acciones HTTP  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] admite las siguientes acciones HTTP para realizar operaciones de creación, lectura, actualización y eliminación en los datos de la entidad que el recurso direccionado representa:  
  
-   **HTTP GET** -esta es la acción predeterminada cuando se tiene acceso a un recurso desde un explorador. No se proporciona ninguna carga en el mensaje de solicitud y se devuelve un método de respuesta con una carga que contiene los datos solicitados.  
  
-   **HTTP POST** -inserta nuevos datos de entidad en el recurso proporcionado. Los datos que se van a insertar se proporcionan en la carga del mensaje de solicitud. La carga del mensaje de respuesta contiene los datos de la entidad recién creada. Esto incluye los valores de clave generados automáticamente. El encabezado también contiene el URI que direcciona el nuevo recurso de entidad.  
  
-   **HTTP DELETE** -elimina los datos de entidad que representa el recurso especificado. En los mensajes de solicitud o respuesta no hay presente ninguna carga.  
  
-   **HTTP PUT** : reemplaza entidad los datos existentes en el recurso solicitado con nuevos datos que se proporcionan en la carga del mensaje de solicitud.  
  
-   **HTTP MERGE** : debido a las ineficacias en la ejecución de una eliminación seguida de una instrucción insert en el origen de datos solo para cambiar los datos de entidad, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] presenta una nueva acción MERGE de HTTP. La carga del mensaje de solicitud contiene las propiedades que se deben cambiar en el recurso de entidad direccionado. Dado que HTTP MERGE no se encuentra definido en la especificación HTTP, puede que sea necesario un procesamiento adicional para enrutar una solicitud HTTP MERGE a través de servidores que no reconocen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
 Para obtener más información, consulte [OData: operaciones](https://go.microsoft.com/fwlink/?LinkId=185792).  
  
### <a name="payload-formats"></a>Formatos de carga  
 Para una solicitud PUT, POST o MERGE de HTTP, la carga de un mensaje de solicitud contiene los datos de entidad que el usuario envía al servicio de datos. El contenido de la carga depende del formato de datos del mensaje. Las respuestas HTTP a todas las acciones, excepto DELETE, también contienen este tipo de carga. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] admite los siguientes formatos de carga para tener acceso y cambiar datos con el servicio:  
  
-   **Atom** -codificación de mensajes basada en XML definida por [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] como una extensión para el protocolo de publicación Atom (AtomPub) para habilitar el intercambio de datos a través de HTTP para fuentes Web, podcasts, wikis y funcionalidad de Internet basado en XML. Para obtener más información, consulte [OData: formato Atom](https://go.microsoft.com/fwlink/?LinkId=185794).  
  
-   **JSON** -JavaScript Object Notation (JSON) es un formato de intercambio de datos ligero que se basa en un subconjunto del lenguaje de programación JavaScript. Para obtener más información, consulte [OData: formato JSON](https://go.microsoft.com/fwlink/?LinkId=185795).  
  
 El formato de mensaje de la carga se solicita en el encabezado del mensaje de la solicitud HTTP. Para obtener más información, consulte [OData: operaciones](https://go.microsoft.com/fwlink/?LinkID=185792).  
  
## <a name="accessing-and-changing-data-using-client-libraries"></a>Acceso y modificación de datos mediante bibliotecas de cliente  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] incluye bibliotecas de cliente que permiten utilizar más fácilmente un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente de .NET Framework y las aplicaciones cliente basadas en Silverlight. Estas bibliotecas simplifican el envío y recepción de los mensajes HTTP. También traducen la carga del mensaje en objetos CLR que representan los datos de entidad. Las bibliotecas cliente representan las dos clases principales <xref:System.Data.Services.Client.DataServiceContext> y <xref:System.Data.Services.Client.DataServiceQuery%601>. Estas clases le permiten consultar un servicio de datos y, a continuación, trabajar con los datos de entidad devueltos como objetos CLR. Para obtener más información, consulte [biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md) y [WCF Data Services (Silverlight)](https://msdn.microsoft.com/library/c0cd9f4b-1372-48e4-9935-c8421239da30).  
  
 Puede usar el **Add Service Reference** cuadro de diálogo de Visual Studio para agregar una referencia a un servicio de datos. Esta herramienta solicita metadatos de servicio desde un servicio de datos al que se ha hecho referencia y genera el <xref:System.Data.Services.Client.DataServiceContext> que representa un servicio de datos, además de generar las clases de servicio de datos cliente que representan las entidades. Para obtener más información, consulte [generar la biblioteca de cliente de servicio de datos](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).  
  
 Hay bibliotecas de programación disponibles que puede usar para consumir un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuentes de distribución en otros tipos de aplicaciones cliente. Para obtener más información, consulte el [SDK de OData](https://go.microsoft.com/fwlink/?LinkId=185796).  
  
## <a name="see-also"></a>Vea también  
 [Acceso a recursos de servicios de datos](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)  
 [Inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
