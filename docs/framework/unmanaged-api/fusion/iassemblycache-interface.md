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
ms.openlocfilehash: df4f0ba018b55202c22cb90b22b927a9c426c4ed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696861"
---
# <a name="iassemblycache-interface"></a>IAssemblyCache (Interfaz)

Representa la caché global de ensamblados para su uso por parte de la tecnología de fusión.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método CreateAssemblyCacheItem](iassemblycache-createassemblycacheitem-method.md)|Obtiene una referencia a una nueva [IAssemblyCacheItem](iassemblycacheitem-interface.md).|  
|[Método CreateAssemblyScavenger](iassemblycache-createassemblyscavenger-method.md)|Reservado para uso interno por parte de la tecnología de fusión.|  
|[Método InstallAssembly](iassemblycache-installassembly-method.md)|Instala el ensamblado especificado en la caché global de ensamblados.|  
|[Método QueryAssemblyInfo](iassemblycache-queryassemblyinfo-method.md)|Obtiene los datos solicitados sobre el ensamblado especificado.|  
|[Método UninstallAssembly](iassemblycache-uninstallassembly-method.md)|Desinstala el ensamblado especificado de la caché global de ensamblados.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de Fusion](fusion-interfaces.md)
- [Caché global de ensamblados](../../app-domains/gac.md)
