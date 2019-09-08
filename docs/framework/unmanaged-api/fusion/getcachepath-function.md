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
ms.openlocfilehash: b1c28f32a4b24393483241bd2d7d6f550b8b65ba
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796909"
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
 [in, out] La longitud máxima solicitada `pwzCachePath`de y, cuando se devuelve, la longitud `pwzCachePath`real de.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Fusion. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ASM_CACHE_FLAGS (enumeración)](asm-cache-flags-enumeration.md)
- [Funciones estáticas globales de la fusión](fusion-global-static-functions.md)
