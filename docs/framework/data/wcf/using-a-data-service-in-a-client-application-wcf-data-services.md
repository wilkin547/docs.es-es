---
title: Usar un servicio de datos en una aplicación cliente (Data Services de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- WCF Data Services, getting started
ms.assetid: 90872d0c-e989-4490-b3e9-54afb10d33d4
ms.openlocfilehash: 050c1a67a367a6dd5175c535fe89fb0010ae8cbc
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790284"
---
# <a name="using-a-data-service-in-a-client-application-wcf-data-services"></a>Usar un servicio de datos en una aplicación cliente (Data Services de WCF)
Puede tener acceso a un servicio que exponga una [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] fuente proporcionando un URI a un explorador Web. El URI proporciona la dirección de un recurso y los mensajes de solicitud se envían a estas direcciones para obtener acceso o cambiar los datos subyacentes que el recurso representa. El explorador emite un comando GET de HTTP y devuelve el recurso solicitado como una fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Para obtener más información, consulte [acceso al servicio desde un explorador Web](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
 Aunque un explorador web puede ser útil para probar que un servicio de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] devuelve los datos esperados, normalmente el acceso a los servicios de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] de producción que le permiten crear, actualizar y eliminar datos también se realiza mediante código de aplicación o lenguajes de scripts en una página web. En este tema se proporciona información general sobre cómo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] obtener acceso a las fuentes desde una aplicación cliente.  
  
## <a name="accessing-and-changing-data-using-rest-semantics"></a>Obtener acceso y cambiar datos mediante la semántica REST  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]ayuda a garantizar la interoperabilidad entre [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] servicios que exponen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuentes y aplicaciones que consumen fuentes. Las aplicaciones tienen acceso a los datos [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]y los cambian en un servicio basado en enviando mensajes de solicitud de una acción http concreta y con un URI que direcciona un recurso de entidad en el que se debe realizar la acción. Cuando sea obligatorio proporcionar datos de la entidad, se proporcionan mediante una carga específicamente codificada en el cuerpo del mensaje.  
  
### <a name="http-actions"></a>Acciones HTTP  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] admite las siguientes acciones HTTP para realizar operaciones de creación, lectura, actualización y eliminación en los datos de la entidad que el recurso direccionado representa:  
  
- **Http Get** : se trata de la acción predeterminada cuando se tiene acceso a un recurso desde un explorador. No se proporciona ninguna carga en el mensaje de solicitud y se devuelve un método de respuesta con una carga que contiene los datos solicitados.  
  
- **Http post** : inserta nuevos datos de entidad en el recurso proporcionado. Los datos que se van a insertar se proporcionan en la carga del mensaje de solicitud. La carga del mensaje de respuesta contiene los datos de la entidad recién creada. Esto incluye los valores de clave generados automáticamente. El encabezado también contiene el URI que direcciona el nuevo recurso de entidad.  
  
- **Http Delete** : elimina los datos de la entidad que representa el recurso especificado. En los mensajes de solicitud o respuesta no hay presente ninguna carga.  
  
- **Put de http** : reemplaza los datos de entidad existentes en el recurso solicitado con nuevos datos que se proporcionan en la carga del mensaje de solicitud.  
  
- **Combinación http** : debido a las ineficiencias en la ejecución de una eliminación seguida de una inserción en el origen de datos solo para [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] cambiar los datos de la entidad, introduce una nueva acción de fusión mediante combinación http. La carga del mensaje de solicitud contiene las propiedades que se deben cambiar en el recurso de entidad direccionado. Dado que HTTP MERGE no se encuentra definido en la especificación HTTP, puede que sea necesario un procesamiento adicional para enrutar una solicitud HTTP MERGE a través de servidores que no reconocen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
 Para obtener más información, [consulte OData: Operaciones](https://go.microsoft.com/fwlink/?LinkId=185792).  
  
### <a name="payload-formats"></a>Formatos de carga  
 Para una solicitud PUT, POST o MERGE de HTTP, la carga de un mensaje de solicitud contiene los datos de entidad que el usuario envía al servicio de datos. El contenido de la carga depende del formato de datos del mensaje. Las respuestas HTTP a todas las acciones, excepto DELETE, también contienen este tipo de carga. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]admite los siguientes formatos de carga para tener acceso a los datos y cambiarlos con el servicio:  
  
- **Atom** : codificación de mensajes basada en XML definida por [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] como una extensión del Protocolo de publicación Atom (AtomPub) para habilitar el intercambio de datos a través de http para fuentes web, podcasts, wikis y funcionalidad de Internet basada en XML. Para obtener más información, [consulte OData: Formato](https://go.microsoft.com/fwlink/?LinkId=185794)Atom.  
  
- **JSON** -notación de objetos JavaScript (JSON) es un formato de intercambio de datos ligero que se basa en un subconjunto del lenguaje de programación JavaScript. Para obtener más información, [consulte OData: Formato](https://go.microsoft.com/fwlink/?LinkId=185795)JSON.  
  
 El formato de mensaje de la carga se solicita en el encabezado del mensaje de la solicitud HTTP. Para obtener más información, [consulte OData: Operaciones](https://go.microsoft.com/fwlink/?LinkID=185792).  
  
## <a name="accessing-and-changing-data-using-client-libraries"></a>Acceso y modificación de datos mediante bibliotecas de cliente  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]incluye bibliotecas de cliente que permiten utilizar más fácilmente una [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente de .NET Framework y aplicaciones cliente basadas en Silverlight. Estas bibliotecas simplifican el envío y recepción de los mensajes HTTP. También traducen la carga del mensaje en objetos CLR que representan los datos de entidad. Las bibliotecas cliente representan las dos clases principales <xref:System.Data.Services.Client.DataServiceContext> y <xref:System.Data.Services.Client.DataServiceQuery%601>. Estas clases le permiten consultar un servicio de datos y, a continuación, trabajar con los datos de entidad devueltos como objetos CLR. Para obtener más información, vea [WCF Data Services biblioteca de cliente](wcf-data-services-client-library.md) y [WCF Data Services (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95)).  
  
 Puede usar el cuadro de diálogo **Agregar referencia de servicio** en Visual Studio para agregar una referencia a un servicio de datos. Esta herramienta solicita metadatos de servicio desde un servicio de datos al que se ha hecho referencia y genera el <xref:System.Data.Services.Client.DataServiceContext> que representa un servicio de datos, además de generar las clases de servicio de datos cliente que representan las entidades. Para obtener más información, vea [generar la biblioteca de cliente del servicio de datos](generating-the-data-service-client-library-wcf-data-services.md).  
  
 Hay bibliotecas de programación disponibles que puede usar para consumir una [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente en otros tipos de aplicaciones cliente. Para obtener más información, vea el [SDK de oData](https://go.microsoft.com/fwlink/?LinkId=185796).  
  
## <a name="see-also"></a>Vea también

- [Acceso a recursos de servicios de datos](accessing-data-service-resources-wcf-data-services.md)
- [Inicio rápido](quickstart-wcf-data-services.md)
