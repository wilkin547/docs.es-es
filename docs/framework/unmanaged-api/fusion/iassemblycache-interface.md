---
title: IAssemblyCache (Interfaz)
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4302a73f9f077c2e1bf4f66c2b80ab025ae4a62c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
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
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [Caché global de ensamblados](../../../../docs/framework/app-domains/gac.md)
