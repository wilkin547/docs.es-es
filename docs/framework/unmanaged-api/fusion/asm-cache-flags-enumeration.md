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
ms.openlocfilehash: 0e3e9da3db71d3e24b2a60ff032a631680055b88
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795275"
---
# <a name="asm_cache_flags-enumeration"></a>ASM_CACHE_FLAGS (Enumeración)
Indica el origen de un ensamblado representado por [IAssemblyCacheItem](iassemblycacheitem-interface.md) en la caché global de ensamblados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|Enumera la memoria caché de ensamblados precompilados mediante Ngen. exe.|  
|`ASM_CACHE_GAC`|Enumera la caché global de ensamblados.|  
|`ASM_CACHE_DOWNLOAD`|Enumera los ensamblados que se han descargado a petición o que se han copiado de la instantánea.|  
|`ASM_CACHE_ROOT`|Indica que la función [GetCachePath (](getcachepath-function.md) debe devolver la ruta de acceso a la caché global de ensamblados para la versión 2,0 de Common Language Runtime (CLR). Solo es significativo en el contexto de una llamada a [GetCachePath (](getcachepath-function.md).|  
|`ASM_CACHE_ROOT_EX`|Indica que la función [GetCachePath (](getcachepath-function.md) debe devolver la ruta de acceso a la caché global de ensamblados para la versión 4 de CLR. Solo es significativo en el contexto de una llamada a [GetCachePath (](getcachepath-function.md).|  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Fusion. h  
  
 **Biblioteca** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [GetCachePath (Función)](getcachepath-function.md)
- [IAssemblyCacheItem (interfaz)](iassemblycacheitem-interface.md)
- [Enumeraciones de fusión](fusion-enumerations.md)
