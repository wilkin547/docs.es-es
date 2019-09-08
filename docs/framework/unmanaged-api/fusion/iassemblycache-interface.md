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
ms.openlocfilehash: 6dab5fe941fce3c23ba718906b29c80c6d257c2f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796771"
---
# <a name="iassemblycache-interface"></a>IAssemblyCache (Interfaz)
Representa la caché global de ensamblados para su uso por parte de la tecnología de fusión.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|[CreateAssemblyCacheItem (método)](iassemblycache-createassemblycacheitem-method.md)|Obtiene una referencia a una nueva [IAssemblyCacheItem](iassemblycacheitem-interface.md).|  
|[CreateAssemblyScavenger (método)](iassemblycache-createassemblyscavenger-method.md)|Reservado para uso interno por parte de la tecnología de fusión.|  
|[InstallAssembly (método)](iassemblycache-installassembly-method.md)|Instala el ensamblado especificado en la caché global de ensamblados.|  
|[QueryAssemblyInfo (método)](iassemblycache-queryassemblyinfo-method.md)|Obtiene los datos solicitados sobre el ensamblado especificado.|  
|[UninstallAssembly (método)](iassemblycache-uninstallassembly-method.md)|Desinstala el ensamblado especificado de la caché global de ensamblados.|  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Fusion. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
- [Caché global de ensamblados](../../app-domains/gac.md)
