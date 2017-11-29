---
title: Proveedores de servicios de datos personalizados (WCF Data Services)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 90e837739edc74ee469f42720f52789ee1c8f6fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="custom-data-service-providers-wcf-data-services"></a>Proveedores de servicios de datos personalizados (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] incluye un conjunto de proveedores que permite definir un modelo de datos basado en tipos de datos enlazados en tiempo de ejecución.  
  
|Proveedor|Descripción|  
|--------------|-----------------|  
|Proveedor de metadatos|Este es el proveedor principal de servicios de datos personalizados que permite definir un modelo de datos personalizado en tiempo de ejecución implementando la interfaz <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>.|  
|Proveedor de consultas|Este proveedor permite ejecutar las consultas sobre un modelo de datos personalizado que se define utilizando la interfaz <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>. El proveedor de consultas se crea implementando la interfaz <xref:System.Data.Services.Providers.IDataServiceQueryProvider>.|  
|Proveedor de actualizaciones|Este proveedor permite realizar actualizaciones a los tipos expuestos en un proveedor de servicio de datos personalizado y administrar la simultaneidad. El proveedor de actualizaciones se crea implementando la interfaz <xref:System.Data.Services.Providers.IDataServiceUpdateProvider>.|  
|Proveedor de paginaciones|Este proveedor se utiliza con el proveedor del servicio de datos personalizado para habilitar la compatibilidad con la paginación controlada por servidor. Un proveedor de paginaciones para un servicio de datos personalizado se crea implementando la interfaz <xref:System.Data.Services.Providers.IDataServicePagingProvider>.|  
|Proveedor de transmisiones por secuencias|Este proveedor permite exponer tipos de datos de objetos binarios grandes como una secuencia. Si implementa la interfaz <xref:System.Data.Services.Providers.IDataServiceStreamProvider>, se crea un proveedor de transmisiones por secuencias. El proveedor de transmisiones por secuencias también se puede utilizar con Entity Framework y proveedores de orígenes de datos de reflexión. Para obtener más información, consulte [proveedor de transmisión por secuencias](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).|  
  
 Para obtener más información, vea el artículo [proveedores de servicios de datos personalizados](http://go.microsoft.com/fwlink/?LinkID=186850) y [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Kit de herramientas de proveedor en el [SDK de OData](http://go.microsoft.com/fwlink/?LinkId=186069).  
  
## <a name="see-also"></a>Vea también  
 [Proveedores de servicios de datos](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Proveedor de Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
 [Proveedor de reflexión](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
