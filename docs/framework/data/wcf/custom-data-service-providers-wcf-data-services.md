---
description: 'Más información acerca de: proveedores de servicios de datos personalizados (Servicios de datos de WCF)'
title: Proveedores de servicios de datos personalizados (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
ms.openlocfilehash: df0cafae46cfdbd71a96341686a9200f032a9938
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766158"
---
# <a name="custom-data-service-providers-wcf-data-services"></a>Proveedores de servicios de datos personalizados (WCF Data Services)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Servicios de datos de WCF incluye un conjunto de proveedores que permite definir un modelo de datos basado en tipos de datos enlazados en tiempo de ejecución.  
  
|Proveedor|Descripción|  
|--------------|-----------------|  
|Proveedor de metadatos|Este es el proveedor principal de servicios de datos personalizados que permite definir un modelo de datos personalizado en tiempo de ejecución implementando la interfaz <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>.|  
|Proveedor de consultas|Este proveedor permite ejecutar las consultas sobre un modelo de datos personalizado que se define utilizando la interfaz <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>. El proveedor de consultas se crea implementando la interfaz <xref:System.Data.Services.Providers.IDataServiceQueryProvider>.|  
|Proveedor de actualizaciones|Este proveedor permite realizar actualizaciones a los tipos expuestos en un proveedor de servicio de datos personalizado y administrar la simultaneidad. El proveedor de actualizaciones se crea implementando la interfaz <xref:System.Data.Services.Providers.IDataServiceUpdateProvider>.|  
|Proveedor de paginaciones|Este proveedor se utiliza con el proveedor del servicio de datos personalizado para habilitar la compatibilidad con la paginación controlada por servidor. Un proveedor de paginaciones para un servicio de datos personalizado se crea implementando la interfaz <xref:System.Data.Services.Providers.IDataServicePagingProvider>.|  
|Proveedor de transmisiones por secuencias|Este proveedor permite exponer tipos de datos de objetos binarios grandes como una secuencia. Si implementa la interfaz <xref:System.Data.Services.Providers.IDataServiceStreamProvider>, se crea un proveedor de transmisiones por secuencias. El proveedor de transmisiones por secuencias también se puede utilizar con Entity Framework y proveedores de orígenes de datos de reflexión. Para obtener más información, consulte [proveedor de streaming](streaming-provider-wcf-data-services.md).|  
  
## <a name="see-also"></a>Vea también

- [Proveedores de Data Services](data-services-providers-wcf-data-services.md)
- [Proveedor de Entity Framework](entity-framework-provider-wcf-data-services.md)
- [Proveedor de reflexión](reflection-provider-wcf-data-services.md)
