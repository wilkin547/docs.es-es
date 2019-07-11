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
# <a name="getcachepath-function"></a><span data-ttu-id="fac85-102">GetCachePath (Función)</span><span class="sxs-lookup"><span data-stu-id="fac85-102">GetCachePath Function</span></span>
<span data-ttu-id="fac85-103">Obtiene la ruta de acceso al ensamblado almacenado en caché, con las marcas especificadas.</span><span class="sxs-lookup"><span data-stu-id="fac85-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fac85-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fac85-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="fac85-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fac85-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="fac85-106">[in] Un [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) valor que indica el origen del ensamblado almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="fac85-106">[in] An [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="fac85-107">[out] El puntero devuelto para la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="fac85-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="fac85-108">[in, out] La longitud máxima solicitada de `pwzCachePath`y cuando se devuelve, la longitud real de `pwzCachePath`.</span><span class="sxs-lookup"><span data-stu-id="fac85-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fac85-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fac85-109">Requirements</span></span>  
 <span data-ttu-id="fac85-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fac85-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fac85-111">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="fac85-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fac85-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fac85-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac85-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="fac85-113">See also</span></span>

- [<span data-ttu-id="fac85-114">ASM_CACHE_FLAGS (enumeración)</span><span class="sxs-lookup"><span data-stu-id="fac85-114">ASM_CACHE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)
- [<span data-ttu-id="fac85-115">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="fac85-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
