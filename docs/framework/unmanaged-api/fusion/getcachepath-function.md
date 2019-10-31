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
# <a name="getcachepath-function"></a><span data-ttu-id="2c475-102">GetCachePath (Función)</span><span class="sxs-lookup"><span data-stu-id="2c475-102">GetCachePath Function</span></span>
<span data-ttu-id="2c475-103">Obtiene la ruta de acceso al ensamblado almacenado en memoria caché, usando las marcas especificadas.</span><span class="sxs-lookup"><span data-stu-id="2c475-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c475-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c475-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c475-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2c475-105">Parameters</span></span>  
 `dwCacheFlags`  
 <span data-ttu-id="2c475-106">de Valor de [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) que indica el origen del ensamblado almacenado en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="2c475-106">[in] An [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="2c475-107">enuncia Puntero devuelto a la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="2c475-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="2c475-108">[in, out] La longitud máxima solicitada de `pwzCachePath`y, cuando se devuelve, la longitud real de `pwzCachePath`.</span><span class="sxs-lookup"><span data-stu-id="2c475-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c475-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c475-109">Requirements</span></span>  
 <span data-ttu-id="2c475-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c475-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c475-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="2c475-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2c475-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c475-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c475-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c475-113">See also</span></span>

- [<span data-ttu-id="2c475-114">ASM_CACHE_FLAGS (enumeración)</span><span class="sxs-lookup"><span data-stu-id="2c475-114">ASM_CACHE_FLAGS Enumeration</span></span>](asm-cache-flags-enumeration.md)
- [<span data-ttu-id="2c475-115">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="2c475-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
