---
description: 'Más información acerca de: GetCachePath ((función)'
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
ms.openlocfilehash: 4f5045d4110ca9aae33ef54eb85a2146f855e6c7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761049"
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
 de [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) valor que indica el origen del ensamblado almacenado en memoria caché.  
  
 `pwzCachePath`  
 enuncia Puntero devuelto a la ruta de acceso.  
  
 `pcchPath`  
 [in, out] La longitud máxima solicitada de `pwzCachePath` y, cuando se devuelve, la longitud real de `pwzCachePath` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ASM_CACHE_FLAGS (Enumeración)](asm-cache-flags-enumeration.md)
- [Funciones estáticas globales de la fusión](fusion-global-static-functions.md)
