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
ms.openlocfilehash: c22f0701cfda4523f595366a97435ef8da08b0cb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724473"
---
# <a name="getcachepath-function"></a><span data-ttu-id="ac043-102">GetCachePath (Función)</span><span class="sxs-lookup"><span data-stu-id="ac043-102">GetCachePath Function</span></span>

<span data-ttu-id="ac043-103">Obtiene la ruta de acceso al ensamblado almacenado en memoria caché, usando las marcas especificadas.</span><span class="sxs-lookup"><span data-stu-id="ac043-103">Gets the path to the cached assembly, using the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac043-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac043-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac043-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac043-105">Parameters</span></span>  

 `dwCacheFlags`  
 <span data-ttu-id="ac043-106">de [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) valor que indica el origen del ensamblado almacenado en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="ac043-106">[in] An [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) value that indicates the source of the cached assembly.</span></span>  
  
 `pwzCachePath`  
 <span data-ttu-id="ac043-107">enuncia Puntero devuelto a la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="ac043-107">[out] The returned pointer to the path.</span></span>  
  
 `pcchPath`  
 <span data-ttu-id="ac043-108">[in, out] La longitud máxima solicitada de `pwzCachePath` y, cuando se devuelve, la longitud real de `pwzCachePath` .</span><span class="sxs-lookup"><span data-stu-id="ac043-108">[in, out] The requested maximum length of `pwzCachePath`, and upon return, the actual length of `pwzCachePath`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac043-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac043-109">Requirements</span></span>  

 <span data-ttu-id="ac043-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac043-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac043-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ac043-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ac043-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac043-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac043-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac043-113">See also</span></span>

- [<span data-ttu-id="ac043-114">ASM_CACHE_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ac043-114">ASM_CACHE_FLAGS Enumeration</span></span>](asm-cache-flags-enumeration.md)
- [<span data-ttu-id="ac043-115">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="ac043-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
