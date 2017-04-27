---
title: "Mitigación: período de bloqueo del grupo | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 92d2de20-79be-4df1-b182-144143a8866a
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2569e6a07ba1456d8bba9b27bf16190e634d6b47
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-pool-blocking-period"></a>Mitigación: período de bloqueo del grupo
El período de bloqueo del grupo de conexiones se quito de las conexiones a bases de datos SQL de Azure.  
  
## <a name="additional-description"></a>Descripción adicional  
 En [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones anteriores, cuando una aplicación encuentra un error de conexión transitorio al conectarse a una base de datos, no es posible reintentar rápidamente la conexión, porque el grupo de conexiones almacena el error en caché y vuelve a generarlo entre 5 segundos y 1 minuto. Para más información, consulte [Agrupaciones de conexiones de SQL Server (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md). Este comportamiento causa problemas en las conexiones a bases de datos SQL de Azure, las que habitualmente presentan errores transitorios de los que se recuperan dentro de unos pocos segundos. La característica de bloqueo del grupo de conexiones significa que la aplicación no se puede conectar a la base de datos durante un período prolongado, incluso si la base de datos está disponible. Este comportamiento es problemático especialmente para las aplicaciones web que se conectan a las bases de datos SQL de Azure y que necesitan presentarse dentro de unos segundos.  
  
 A partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], para las solicitudes de apertura de conexión a bases de datos SQL de Azure conocidas (*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de), los errores al abrir las conexiones no se almacenan en caché. Para todos los otros intentos de conexión, se sigue aplicando el período de bloqueo del grupo de conexiones.  
  
## <a name="impact"></a>Impacto  
 Este cambio permite que el intento de abrir una conexión a las bases de datos SQL de Azure se reintente de inmediato, lo que mejora el rendimiento de las aplicaciones habilitadas para la nube.  
  
## <a name="mitigation"></a>Mitigación  
 En el caso de las aplicaciones a las que este cambio afecta negativamente, puede configurar el período de bloqueo del grupo de conexiones si establece la nueva propiedad <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A>.  El valor de la propiedad es un miembro de la enumeración <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=fullName> que puede tomar uno de estos tres valores:  
  
-   `PoolBlockingPeriod.AlwaysBlock` 
  
-   `PoolBlockingPeriod.Auto`  
  
-   `PoolBlockingPeriod.NeverBlock` 
  
 Puede restaurar el comportamiento anterior si establece la propiedad <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> en `PoolBlockingPeriod.AlwaysBlock`.  
  
## <a name="see-also"></a>Vea también  
 [Cambios en el runtime](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)
