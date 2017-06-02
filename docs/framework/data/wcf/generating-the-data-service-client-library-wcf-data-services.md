---
title: "Generar la biblioteca de cliente del servicio de datos (WCF Data Services) | Microsoft Docs"
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
  - "Agregar referencia de servicio, cuadro de diálogo"
  - "aplicaciones cliente, Servicios de datos de Microsoft WCF"
  - "WCF Data Services, biblioteca de cliente"
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Generar la biblioteca de cliente del servicio de datos (WCF Data Services)
Un servicio de datos que implementa [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] puede devolver un documento de metadatos del servicio que describe el modelo de datos expuesto por la fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  Para obtener más información, vea el tema sobre [OData: documento de metadatos del servicio](http://go.microsoft.com/fwlink/?LinkId=186070). Puede usar el cuadro de diálogo **Agregar referencia de servicio** de Visual Studio para agregar una referencia a un servicio basado en [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  Cuando se usa esta herramienta para agregar una referencia a los metadatos que se devuelven en una fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] en un proyecto de cliente, realiza las acciones siguientes:  
  
-   Solicita el documento de metadatos del servicio al servicio de datos e interpreta los metadatos devueltos.  
  
    > [!NOTE]
    >  Los metadatos devueltos se almacenan en el proyecto de cliente como un archivo .edmx.  Este archivo .edmx no se puede abrir utilizando el diseñador de Entity Data Model ya que no tiene el mismo formato que un archivo .edmx utilizado por Entity Framework.  Puede ver este archivo de metadatos utilizando el editor XML o cualquier editor de texto.  Para obtener más información, vea la especificación [\[MC\-EDMX\]: Entity Data Model for Data Services Packaging Format](http://go.microsoft.com/fwlink/?LinkID=178833).  
  
-   Genera una representación del servicio como una clase de contenedor de entidades que hereda de <xref:System.Data.Services.Client.DataServiceContext>.  Esta clase de contenedor de entidades generada es similar al contenedor de entidades generado por las herramientas de Entity Data Model.  Para obtener más información, consulta [Object Services Overview \(Entity Framework\)](http://msdn.microsoft.com/es-es/43014cf9-c9cb-4538-bfbb-197820b60038).  
  
-   Genera clases de datos para los tipos de modelo de entidad que detecta en los metadatos del servicio.  
  
-   Agrega al proyecto una referencia al ensamblado `System.Data.Services.Client`.  
  
 Para obtener más información, consulta [Cómo: Agregar una referencia a un servicio de datos](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  
  
 Las clases del servicio de datos del cliente también se pueden generar usando la herramienta [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) en el símbolo del sistema.  Para obtener más información, consulta [Cómo: Generar manualmente clases del servicio de datos del cliente](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## Asignación de tipos de datos del cliente  
 Cuando se usa el cuadro de diálogo **Agregar referencia de servicio** en Visual Studio o la herramienta `DataSvcUtil.exe` para generar clases de datos del cliente que se basan en una fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], los tipos de datos de .NET Framework se asignan a los tipos primitivos del modelo de datos de la siguiente forma:  
  
|Tipo del modelo de datos|Tipo de datos de .NET Framework|  
|------------------------------|-------------------------------------|  
|`Edm.Binary`|<xref:System.Byte> `[]`|  
|`Edm.Boolean`|<xref:System.Boolean>|  
|`Edm.Byte`|<xref:System.Byte>|  
|`Edm.DateTime`|<xref:System.DateTime>|  
|`Edm.Decimal`|<xref:System.Decimal>|  
|`Edm.Double`|<xref:System.Double>|  
|`Edm.Guid`|<xref:System.Guid>|  
|`Edm.Int16`|<xref:System.Int16>|  
|`Edm.Int32`|<xref:System.Int32>|  
|`Edm.Int64`|<xref:System.Int64>|  
|`Edm.SByte`|<xref:System.SByte>|  
|`Edm.Single`|<xref:System.Single>|  
|`Edm.String`|<xref:System.String>|  
  
 Para obtener más información, vea el tema sobre [OData: tipos de datos primitivos](http://go.microsoft.com/fwlink/?LinkId=186072).  
  
## Vea también  
 [Biblioteca de cliente de WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)   
 [Inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)