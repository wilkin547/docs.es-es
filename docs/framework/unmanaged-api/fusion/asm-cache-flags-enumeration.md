---
title: ASM_CACHE_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 619643eb50abc75fd10d59b38767013b2617c8cf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077782"
---
# <a name="asmcacheflags-enumeration"></a>ASM_CACHE_FLAGS (Enumeración)
Indica el origen de un ensamblado que se representa mediante [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) en la caché global de ensamblados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|Enumera la caché de ensamblados precompilados mediante el uso de Ngen.exe.|  
|`ASM_CACHE_GAC`|Enumera la caché global de ensamblados.|  
|`ASM_CACHE_DOWNLOAD`|Enumera los ensamblados que se han descargado bajo demanda o que han sido copia sombra.|  
|`ASM_CACHE_ROOT`|Indica que el [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) función debe devolver la ruta de acceso a la caché global de ensamblados de common language runtime (CLR) versión 2.0. Solo tiene sentido en el contexto de una llamada a [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).|  
|`ASM_CACHE_ROOT_EX`|Indica que el [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) función debe devolver la ruta de acceso a la caché global de ensamblados para la versión 4 de CLR. Solo tiene sentido en el contexto de una llamada a [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Fusion.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetCachePath (Función)](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)
- [IAssemblyCacheItem (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
- [Enumeraciones de fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
