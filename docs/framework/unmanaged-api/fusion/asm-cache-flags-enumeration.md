---
description: 'Más información acerca de: enumeración ASM_CACHE_FLAGS'
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
ms.openlocfilehash: 866f61d2960074495ed036e3a8e89ebceec74e87
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761439"
---
# <a name="asm_cache_flags-enumeration"></a><span data-ttu-id="f6ab2-103">ASM_CACHE_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f6ab2-103">ASM_CACHE_FLAGS Enumeration</span></span>

<span data-ttu-id="f6ab2-104">Indica el origen de un ensamblado representado por [IAssemblyCacheItem](iassemblycacheitem-interface.md) en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="f6ab2-104">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6ab2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6ab2-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="f6ab2-106">Members</span><span class="sxs-lookup"><span data-stu-id="f6ab2-106">Members</span></span>  
  
|<span data-ttu-id="f6ab2-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="f6ab2-107">Member</span></span>|<span data-ttu-id="f6ab2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6ab2-108">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="f6ab2-109">Enumera la memoria caché de ensamblados precompilados mediante Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="f6ab2-109">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="f6ab2-110">Enumera la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="f6ab2-110">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="f6ab2-111">Enumera los ensamblados que se han descargado a petición o que se han copiado de la instantánea.</span><span class="sxs-lookup"><span data-stu-id="f6ab2-111">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="f6ab2-112">Indica que la función [GetCachePath (](getcachepath-function.md) debe devolver la ruta de acceso a la caché global de ensamblados para la versión 2,0 de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f6ab2-112">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="f6ab2-113">Solo es significativo en el contexto de una llamada a [GetCachePath (](getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="f6ab2-113">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="f6ab2-114">Indica que la función [GetCachePath (](getcachepath-function.md) debe devolver la ruta de acceso a la caché global de ensamblados para la versión 4 de CLR.</span><span class="sxs-lookup"><span data-stu-id="f6ab2-114">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="f6ab2-115">Solo es significativo en el contexto de una llamada a [GetCachePath (](getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="f6ab2-115">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f6ab2-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6ab2-116">Requirements</span></span>  

 <span data-ttu-id="f6ab2-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6ab2-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6ab2-118">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="f6ab2-118">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f6ab2-119">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f6ab2-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6ab2-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6ab2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ab2-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6ab2-121">See also</span></span>

- [<span data-ttu-id="f6ab2-122">GetCachePath (Función)</span><span class="sxs-lookup"><span data-stu-id="f6ab2-122">GetCachePath Function</span></span>](getcachepath-function.md)
- [<span data-ttu-id="f6ab2-123">IAssemblyCacheItem (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6ab2-123">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
- [<span data-ttu-id="f6ab2-124">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="f6ab2-124">Fusion Enumerations</span></span>](fusion-enumerations.md)
