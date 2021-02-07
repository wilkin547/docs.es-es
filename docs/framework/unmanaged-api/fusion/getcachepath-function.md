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
# <a name="getcachepath-function"></a><span data-ttu-id="4033c-103">GetCachePath (Función)</span><span class="sxs-lookup"><span data-stu-id="4033c-103">GetCachePath Function</span></span>

<span data-ttu-id="4033c-104">Obtiene la ruta de acceso al ensamblado almacenado en memoria caché, usando las marcas especificadas.</span><span class="sxs-lookup"><span data-stu-id="4033c-104">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4033c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4033c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="4033c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4033c-106">Parameters</span></span>  

 `dwCacheFlags`  
 <span data-ttu-id="4033c-107">de [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) valor que indica el origen del ensamblado almacenado en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="4033c-107">[in] An [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="4033c-108">enuncia Puntero devuelto a la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4033c-108">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="4033c-109">[in, out] La longitud máxima solicitada de `pwzCachePath` y, cuando se devuelve, la longitud real de `pwzCachePath` .</span><span class="sxs-lookup"><span data-stu-id="4033c-109">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4033c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4033c-110">Requirements</span></span>  

 <span data-ttu-id="4033c-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4033c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4033c-112">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="4033c-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4033c-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4033c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4033c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4033c-114">See also</span></span>

- [<span data-ttu-id="4033c-115">ASM_CACHE_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4033c-115">ASM_CACHE_FLAGS Enumeration</span></span>](asm-cache-flags-enumeration.md)
- [<span data-ttu-id="4033c-116">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="4033c-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
