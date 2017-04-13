---
title: "Detalles de implementaci&#243;n del protocolo WCF Data Services | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 712d689b-fada-4cbb-bcdb-d65a3ef83b4c
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Detalles de implementaci&#243;n del protocolo WCF Data Services
## Detalles de implementación del protocolo OData  
 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] requiere que un servicio de datos que implementa el protocolo proporcione un cierto conjunto mínimo de funcionalidades.  Estas funcionalidades se describen en los documentos del protocolo en términos de "debería" y "es preciso". Otras funcionalidades opcionales se describen en términos de "es posible". Este tema aborda estas funcionalidades opcionales que en estos momentos no implementa [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  Para obtener más información, vea el tema sobre [la documentación del protocolo de OData](http://go.microsoft.com/fwlink/?LinkID=184554).  
  
### Compatibilidad con la opción de consulta $format  
 El protocolo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] admite fuentes Notación de objetos JavaScript \(JSON\) y Atom, y [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] proporciona la opción de consulta del sistema `$format` para permitir a un cliente solicitar el formato de la fuente de respuesta.  Esta opción de consulta del sistema, si el servicio de datos la admite, debe invalidar el valor del encabezado Accept de la solicitud.  [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] admite devolver fuentes tanto JSON como Atom.  Sin embargo, la implementación predeterminada no admite la opción de consulta `$format` y usa solo el valor del encabezado Accept para determinar el formato de la respuesta.  Hay casos en los que el servicio de datos quizás necesite admitir la opción de consulta `$format`, como cuando los clientes no pueden establecer el encabezado Accept.  Para admitir estos escenarios, debe extender su servicio de datos para administrar esta opción en el URI.  Puede agregar esta funcionalidad al servicio de datos descargando el proyecto de ejemplo [Compatibilidad con el formato controlado por JSONP y URL para ADO.NET Data Services](http://go.microsoft.com/fwlink/?LinkId=208228) del sitio web Galería de código de MSDN y agregándolo a su proyecto de servicio de datos.  Este ejemplo quita la opción de consulta `$format` y cambia el encabezado Accept a `application/json`.  Al incluir el proyecto de ejemplo y agregar `JSONPSupportBehaviorAttribute` a la clase del servicio de datos permite al servicio administrar la opción de consulta `$format` `$format=json`.  Se requiere mayor personalización de este proyecto de ejemplo para administrar también `$format=atom` u otros formatos personalizados.  
  
## Comportamientos de WCF Data Services  
 El protocolo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] no define explícitamente los siguientes comportamientos de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]:  
  
### Comportamiento de ordenación predeterminado  
 Cuando una solicitud de consulta que se envía al servicio de datos incluye una opción de consulta del sistema `$top` o `$skip` y no incluye la opción de consulta del sistema `$orderby`, las propiedades clave ordenan la fuente devuelta en sentido ascendente.  Esto es porque se necesita la ordenación para asegurar la correcta paginación de los resultados.  Para ello, el servicio de datos agrega una expresión de ordenación a la consulta.  Este comportamiento también se produce cuando la paginación controlada por servidor está habilitada en el servicio de datos.  Para obtener más información, vea [Configurar el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md). Para controlar la clasificación de la fuente devuelta, debería incluir `$orderby` en el URI de consulta.  
  
## Vea también  
 [Definir WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [Biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)