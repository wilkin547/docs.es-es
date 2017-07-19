---
title: "Exponer los datos como servicio (WCF Data Services) | Microsoft Docs"
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
  - "introducción, Servicios de datos de Microsoft WCF"
  - "Servicios de datos de Microsoft WCF, configurar"
  - "WCF Data Services, introducción"
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Exponer los datos como servicio (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] se integra con Visual Studio para permitirle definir con más facilidad servicios para exponer los datos como fuentes [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)].  La creación de un servicio de datos que expone una fuente [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] supone la realización de los siguientes pasos básicos:  
  
1.  **Definir** **el modelo de datos**.  [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] admite de forma nativa los modelos de datos basados en [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md).  Para obtener más información, consulta [Cómo: Crear un servicio de datos mediante un origen de datos de ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).  
  
     [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] también admite modelos de datos que están basados en los objetos de Common Language Runtime \(CLR\) que devuelven una instancia de la interfaz <xref:System.Linq.IQueryable%601>.  Esto le permite implementar servicios de datos que están basados en listas, matrices y colecciones de .NET Framework. Para permitir operaciones de creación, actualización y eliminación sobre estas estructuras de datos, también debe implementar la interfaz <xref:System.Data.Services.IUpdatable>.  Para obtener más información, consulta [Cómo: Crear un servicio de datos mediante el proveedor de reflexión](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).  
  
     Para escenarios más avanzados, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] incluye un conjunto de proveedores que le permiten definir un modelo de datos basado en tipos de datos enlazados en tiempo de ejecución.  Para obtener más información, consulta [Proveedores de servicios de datos personalizados](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).  
  
2.  **Crear el servicio de datos.** El servicio de datos más básico expone una clase que hereda de la clase <xref:System.Data.Services.DataService%601>, con un tipo `T` que es el nombre completo del espacio de nombres del contenedor de la entidad.  Para obtener más información, consulta [Definir WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
3.  **Configurar el servicio de datos.** De forma predeterminada, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] deshabilita el acceso a los recursos expuestos por un contenedor de entidades. La interfaz <xref:System.Data.Services.DataServiceConfiguration> le permite configurar el acceso a recursos y operaciones de servicio, especificar la versión admitida de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] y definir otros comportamientos de todo el servicio, como los comportamientos de las operaciones por lotes o el número máximo de entidades que se pueden devolver en una única respuesta. Para obtener más información, vea [Configurar el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 Para obtener un ejemplo de cómo crear un servicio de datos simple basado en la base de datos de ejemplo Northwind, vea [Inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Vea también  
 [Introducción](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)   
 [Información general](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)