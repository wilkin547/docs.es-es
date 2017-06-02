---
title: "Usar un servicio de datos en una aplicaci&#243;n cliente (WCF Data Services) | Microsoft Docs"
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
  - "Servicios de datos de Microsoft WCF, biblioteca de cliente"
  - "WCF Data Services, introducción"
ms.assetid: 90872d0c-e989-4490-b3e9-54afb10d33d4
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Usar un servicio de datos en una aplicaci&#243;n cliente (WCF Data Services)
Es posible tener acceso a un servicio que exponga una fuente de [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] si se proporciona un URI a un explorador web.  El URI proporciona la dirección de un recurso y los mensajes de solicitud se envían a estas direcciones para obtener acceso o cambiar los datos subyacentes que el recurso representa.  El explorador emite un comando GET de HTTP y devuelve el recurso solicitado como una fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  Para obtener más información, consulta [Obtener acceso al servicio desde un explorador web](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
 Aunque un explorador web puede ser útil para probar que un servicio de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] devuelve los datos esperados, normalmente el acceso a los servicios de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] de producción que le permiten crear, actualizar y eliminar datos también se realiza mediante código de aplicación o lenguajes de scripts en una página web.  En este tema se proporciona información general acerca de cómo obtener acceso a las fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] desde una aplicación cliente.  
  
## Obtener acceso y cambiar datos mediante la semántica REST  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] ayuda a garantizar la interoperabilidad entre servicios que exponen fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] y aplicaciones que consumen fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Las aplicaciones obtienen acceso y modifican datos en un servicio basado en [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] enviando mensajes de solicitud de una acción HTTP concreta y con un URI que direcciona un recurso de entidad en el que se debe realizar la acción.  Cuando sea obligatorio proporcionar datos de la entidad, se proporcionan mediante una carga específicamente codificada en el cuerpo del mensaje.  
  
### Acciones HTTP  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] admite las siguientes acciones HTTP para realizar operaciones de creación, lectura, actualización y eliminación en los datos de la entidad que el recurso direccionado representa:  
  
-   **GET de HTTP**: es la acción predeterminada cuando se tiene acceso a un recurso desde un explorador.  No se proporciona ninguna carga en el mensaje de solicitud y se devuelve un método de respuesta con una carga que contiene los datos solicitados.  
  
-   **POST de HTTP**: inserta los nuevos datos de entidad en el recurso proporcionado.  Los datos que se van a insertar se proporcionan en la carga del mensaje de solicitud.  La carga del mensaje de respuesta contiene los datos de la entidad recién creada.  Esto incluye los valores de clave generados automáticamente.  El encabezado también contiene el URI que direcciona el nuevo recurso de entidad.  
  
-   **DELETE de HTTP**: elimina los datos de entidad que representa el recurso especificado.  En los mensajes de solicitud o respuesta no hay presente ninguna carga.  
  
-   **PUT de HTTP**: reemplaza los datos de la entidad existentes en el recurso solicitado con nuevos datos que se proporcionan en la carga del mensaje de solicitud.  
  
-   **MERGE de HTTP**: debido a las ineficacias a la hora de ejecutar una acción DELETE seguida de una acción INSERT en el origen de datos únicamente para cambiar los datos de entidad, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] presenta una nueva acción MERGE de HTTP.  La carga del mensaje de solicitud contiene las propiedades que se deben cambiar en el recurso de entidad direccionado.  Dado que HTTP MERGE no se encuentra definido en la especificación HTTP, puede que sea necesario un procesamiento adicional para enrutar una solicitud HTTP MERGE a través de servidores que no reconocen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
 Para obtener más información, vea el tema sobre [OData: operaciones](http://go.microsoft.com/fwlink/?LinkId=185792).  
  
### Formatos de carga  
 Para una solicitud PUT, POST o MERGE de HTTP, la carga de un mensaje de solicitud contiene los datos de entidad que el usuario envía al servicio de datos.  El contenido de la carga depende del formato de datos del mensaje.  Las respuestas HTTP a todas las acciones, excepto DELETE, también contienen este tipo de carga.  [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] admite los siguientes formatos de carga para tener acceso y cambiar los datos con el servicio:  
  
-   **Atom**: codificación de mensajes basada en XML definida por [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] como una extensión del Protocolo de publicación Atom \(AtomPub\) para habilitar el intercambio de datos sobre HTTP para fuentes web, podcasts, wikis y funcionalidad de Internet basada en XML.  Para obtener más información, vea el tema sobre [OData: formato Atom](http://go.microsoft.com/fwlink/?LinkId=185794).  
  
-   **JSON**: JavaScript Object Notation \(JSON\) es un formato de intercambio de datos ligero que está basado en un subconjunto del lenguaje de programación JavaScript.  Para obtener más información, vea el tema sobre [OData: formato JSON](http://go.microsoft.com/fwlink/?LinkId=185795).  
  
 El formato de mensaje de la carga se solicita en el encabezado del mensaje de la solicitud HTTP.  Para obtener más información, vea el tema sobre [OData: operaciones](http://go.microsoft.com/fwlink/?LinkID=185792).  
  
## Acceso y modificación de datos mediante bibliotecas de cliente  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] incluye bibliotecas de cliente que permiten utilizar más fácilmente una fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] en .NET Framework y las aplicaciones cliente basadas en Silverlight.  Estas bibliotecas simplifican el envío y recepción de los mensajes HTTP.  También traducen la carga del mensaje en objetos CLR que representan los datos de entidad.  Las bibliotecas cliente representan las dos clases principales <xref:System.Data.Services.Client.DataServiceContext> y <xref:System.Data.Services.Client.DataServiceQuery%601>.  Estas clases le permiten consultar un servicio de datos y, a continuación, trabajar con los datos de entidad devueltos como objetos CLR.  Para obtener más información, vea [Biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md) y [WCF Data Services \(Silverlight\)](http://msdn.microsoft.com/es-es/c0cd9f4b-1372-48e4-9935-c8421239da30).  
  
 Puede usar el cuadro de diálogo **Agregar referencia de servicio** de Visual Studio para agregar una referencia a un servicio de datos.  Esta herramienta solicita metadatos de servicio desde un servicio de datos al que se ha hecho referencia y genera el <xref:System.Data.Services.Client.DataServiceContext> que representa un servicio de datos, además de generar las clases de servicio de datos cliente que representan las entidades.  Para obtener más información, consulta [Generar la biblioteca de cliente del servicio de datos](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).  
  
 Existen bibliotecas de programación que permiten utilizar una fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] en otros tipos de aplicaciones cliente.  Para obtener más información, vea el tema sobre el [SDK de OData](http://go.microsoft.com/fwlink/?LinkId=185796).  
  
## Vea también  
 [Acceso a recursos del servicio de datos](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)   
 [Inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)