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
ms.openlocfilehash: 13e1468ef5a48f18910c1f8082cdd7c4849da14a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132691"
---
# <a name="getcachepath-function"></a>GetCachePath (Función)
Obtiene la ruta de acceso al ensamblado almacenado en memoria caché, usando las marcas especificadas.  
  
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
 de Valor de [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) que indica el origen del ensamblado almacenado en memoria caché.  
  
 `pwzCachePath`  
 enuncia Puntero devuelto a la ruta de acceso.  
  
 `pcchPath`  
 [in, out] La longitud máxima solicitada de `pwzCachePath`y, cuando se devuelve, la longitud real de `pwzCachePath`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ASM_CACHE_FLAGS (enumeración)](asm-cache-flags-enumeration.md)
- [Funciones estáticas globales de la fusión](fusion-global-static-functions.md)
