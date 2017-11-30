---
title: IAssemblyCache (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCache
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCache
helpviewer_keywords: IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6244e6c3b0cc88c50cda050a480f5af5b3996b47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iassemblycache-interface"></a>IAssemblyCache (Interfaz)
Representa la caché global de ensamblados para su uso por la tecnología de fusión.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateAssemblyCacheItem (método)](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|Obtiene una referencia a una nueva [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).|  
|[CreateAssemblyScavenger (método)](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|Reservado para uso interno por la tecnología fusion.|  
|[InstallAssembly (método)](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|Instala al ensamblado especificado en la caché global de ensamblados.|  
|[QueryAssemblyInfo (método)](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|Obtiene los datos solicitados sobre el ensamblado especificado.|  
|[UninstallAssembly (método)](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|Desinstala el ensamblado especificado de la caché global de ensamblados.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Fusion.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [Caché global de ensamblados](../../../../docs/framework/app-domains/gac.md)
