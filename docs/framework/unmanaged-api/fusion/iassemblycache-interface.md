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
ms.openlocfilehash: 9fc5f3a3d5bc5699a596bcc648a7153190c130f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075644"
---
# <a name="iassemblycache-interface"></a>IAssemblyCache (Interfaz)
Representa la caché global de ensamblados para su uso por la tecnología fusion.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método CreateAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|Obtiene una referencia a un nuevo [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).|  
|[Método CreateAssemblyScavenger](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|Reservado para uso interno por la tecnología fusion.|  
|[Método InstallAssembly](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|Instala al ensamblado especificado en la caché global de ensamblados.|  
|[Método QueryAssemblyInfo](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|Obtiene los datos solicitados sobre el ensamblado especificado.|  
|[Método UninstallAssembly](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|Desinstala el ensamblado especificado de la caché global de ensamblados.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Fusion.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [Caché global de ensamblados](../../../../docs/framework/app-domains/gac.md)
