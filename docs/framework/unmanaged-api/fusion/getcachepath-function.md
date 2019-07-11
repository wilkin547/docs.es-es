---
title: GetCachePath (Función)
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92366190c769344b41923cbb25ed4b04afceaae9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778668"
---
# <a name="getcachepath-function"></a>GetCachePath (Función)
Obtiene la ruta de acceso al ensamblado almacenado en caché, con las marcas especificadas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwCacheFlags`  
 [in] Un [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) valor que indica el origen del ensamblado almacenado en caché.  
  
 `pwzCachePath`  
 [out] El puntero devuelto para la ruta de acceso.  
  
 `pcchPath`  
 [in, out] La longitud máxima solicitada de `pwzCachePath`y cuando se devuelve, la longitud real de `pwzCachePath`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Fusion.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ASM_CACHE_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)
- [Funciones estáticas globales de la fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
