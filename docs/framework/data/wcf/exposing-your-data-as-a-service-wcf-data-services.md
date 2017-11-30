---
title: Exponer los datos como servicio (Data Services de WCF)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 122d05d5e4bd7690f32b22453dccbfaab2fb7f13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="exposing-your-data-as-a-service-wcf-data-services"></a>Exponer los datos como servicio (Data Services de WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]se integra con Visual Studio que le permite definir con más facilidad servicios para exponer los datos como [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] fuentes de distribución. Crear un servicio de datos que expone un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] fuente implica los siguientes pasos básicos:  
  
1.  **Definir** **el modelo de datos**. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]admite de forma nativa los modelos de datos que se basan en el [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md). Para obtener más información, consulte [Cómo: crear un servicio de datos mediante un origen de datos de ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).  
  
     [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] también admite modelos de datos que están basados en los objetos de Common Language Runtime (CLR) que devuelven una instancia de la interfaz <xref:System.Linq.IQueryable%601>. Esto permite implementar servicios de datos que están basados en listas, matrices y colecciones en .NET Framework. Para habilitar las operaciones de creación, actualización y eliminación sobre estas estructuras de datos, también debe implementar la interfaz <xref:System.Data.Services.IUpdatable>. Para obtener más información, consulte [Cómo: crear un servicio de datos mediante el proveedor de reflexión](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).  
  
     Para escenarios más avanzados, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] incluye un conjunto de proveedores que le permiten definir un modelo de datos basado en tipos de datos en tiempo de ejecución. Para obtener más información, consulte [proveedores de servicios de datos personalizados](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).  
  
2.  **Crear el servicio de datos.** El servicio de datos más básico expone una clase que hereda de la clase <xref:System.Data.Services.DataService%601> , con un tipo `T` que es el nombre completo del espacio de nombres del contenedor de la entidad. Para obtener más información, consulta [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
3.  **Configurar el servicio de datos.** De forma predeterminada, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] deshabilita el acceso a los recursos que expone un contenedor de entidades. La interfaz <xref:System.Data.Services.DataServiceConfiguration> le permite configurar el acceso a los recursos y las operaciones del servicio, especificar la versión admitida de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], así como definir otros comportamientos de todo el servicio, como los comportamientos de las operaciones por lotes o el número máximo de entidades que pueden devolverse en una única respuesta. Para obtener más información, consulte [configurar el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 Para obtener un ejemplo de cómo crear un servicio de datos simple que se basa en la base de datos de ejemplo Northwind, vea [inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="see-also"></a>Vea también  
 [Introducción](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 [Información general](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)
