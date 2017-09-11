---
title: "Mitigación: período de bloqueo del grupo"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: caaaafaff44f2a679b16fe3f1aae59bcf717388e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-pool-blocking-period"></a><span data-ttu-id="f1c00-102">Mitigación: período de bloqueo del grupo</span><span class="sxs-lookup"><span data-stu-id="f1c00-102">Mitigation: Pool Blocking Period</span></span>
<span data-ttu-id="f1c00-103">El período de bloqueo del grupo de conexiones se quito de las conexiones a bases de datos SQL de Azure.</span><span class="sxs-lookup"><span data-stu-id="f1c00-103">The connection pool blocking period has been removed for connections to Azure SQL databases.</span></span>  
  
## <a name="additional-description"></a><span data-ttu-id="f1c00-104">Descripción adicional</span><span class="sxs-lookup"><span data-stu-id="f1c00-104">Additional description</span></span>  
 <span data-ttu-id="f1c00-105">En [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y versiones anteriores, cuando una aplicación encuentra un error de conexión transitorio al conectarse a una base de datos, no es posible reintentar rápidamente la conexión, porque el grupo de conexiones almacena el error en caché y vuelve a generarlo entre 5 segundos y 1 minuto. Para más información, consulte [Agrupaciones de conexiones de SQL Server (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="f1c00-105">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, when an app encounters a transient connection failure when connecting to a database, the connection attempt cannot be retried quickly, because the connection pool caches the error and re-throws it for 5 seconds to 1 min. For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span> <span data-ttu-id="f1c00-106">Este comportamiento causa problemas en las conexiones a bases de datos SQL de Azure, las que habitualmente presentan errores transitorios de los que se recuperan dentro de unos pocos segundos.</span><span class="sxs-lookup"><span data-stu-id="f1c00-106">This behavior is problematic for connections to Azure SQL databases, which often fail with transient errors that are typically recovered from within a few seconds.</span></span> <span data-ttu-id="f1c00-107">La característica de bloqueo del grupo de conexiones significa que la aplicación no se puede conectar a la base de datos durante un período prolongado, incluso si la base de datos está disponible.</span><span class="sxs-lookup"><span data-stu-id="f1c00-107">The connection pool blocking feature means that the app cannot connect to the database for an extensive period, even though the database is available.</span></span> <span data-ttu-id="f1c00-108">Este comportamiento es problemático especialmente para las aplicaciones web que se conectan a las bases de datos SQL de Azure y que necesitan presentarse dentro de unos segundos.</span><span class="sxs-lookup"><span data-stu-id="f1c00-108">This behavior is particularly problematic for web apps that connect to Azure SQL databases and that need to render within a few seconds.</span></span>  
  
 <span data-ttu-id="f1c00-109">A partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], para las solicitudes de apertura de conexión a bases de datos SQL de Azure conocidas (*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de), los errores al abrir las conexiones no se almacenan en caché.</span><span class="sxs-lookup"><span data-stu-id="f1c00-109">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], for connection open requests to known Azure SQL databases (*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de), connection open errors are not cached.</span></span> <span data-ttu-id="f1c00-110">Para todos los otros intentos de conexión, se sigue aplicando el período de bloqueo del grupo de conexiones.</span><span class="sxs-lookup"><span data-stu-id="f1c00-110">For all other connection attempts, the connection pool blocking period continues to be enforced.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="f1c00-111">Impacto</span><span class="sxs-lookup"><span data-stu-id="f1c00-111">Impact</span></span>  
 <span data-ttu-id="f1c00-112">Este cambio permite que el intento de abrir una conexión a las bases de datos SQL de Azure se reintente de inmediato, lo que mejora el rendimiento de las aplicaciones habilitadas para la nube.</span><span class="sxs-lookup"><span data-stu-id="f1c00-112">This change allows the connection open attempt to be retried immediately for Azure SQL databases, thereby improving the performance of cloud-enabled apps.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="f1c00-113">Mitigación</span><span class="sxs-lookup"><span data-stu-id="f1c00-113">Mitigation</span></span>  
 <span data-ttu-id="f1c00-114">En el caso de las aplicaciones a las que este cambio afecta negativamente, puede configurar el período de bloqueo del grupo de conexiones si establece la nueva propiedad <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A>.</span><span class="sxs-lookup"><span data-stu-id="f1c00-114">For apps that are adversely affected by this change, the connection pool blocking period can be configured by setting the new <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> property.</span></span>  <span data-ttu-id="f1c00-115">El valor de la propiedad es un miembro de la enumeración <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=fullName> que puede tener cualquiera de los tres valores:</span><span class="sxs-lookup"><span data-stu-id="f1c00-115">The value of the property is a member of the <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=fullName> enumeration that can take either of three values:</span></span>  
  
-   `PoolBlockingPeriod.AlwaysBlock` 
  
-   `PoolBlockingPeriod.Auto`  
  
-   `PoolBlockingPeriod.NeverBlock` 
  
 <span data-ttu-id="f1c00-116">El comportamiento anterior se puede restaurar al establecer la propiedad <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> en `PoolBlockingPeriod.AlwaysBlock`.</span><span class="sxs-lookup"><span data-stu-id="f1c00-116">The previous behavior can be restored by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> property to `PoolBlockingPeriod.AlwaysBlock`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c00-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1c00-117">See Also</span></span>  
 [<span data-ttu-id="f1c00-118">Cambios en el runtime</span><span class="sxs-lookup"><span data-stu-id="f1c00-118">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)

