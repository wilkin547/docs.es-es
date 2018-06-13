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
ms.openlocfilehash: ddf0f01db73a873d2dd823e1f754b970ae8aa056
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430478"
---
# <a name="asmcacheflags-enumeration"></a><span data-ttu-id="5015a-102">ASM_CACHE_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="5015a-102">ASM_CACHE_FLAGS Enumeration</span></span>
<span data-ttu-id="5015a-103">Indica que el origen de un ensamblado que se representa mediante [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5015a-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5015a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5015a-104">Syntax</span></span>  
  
```  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="5015a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5015a-105">Members</span></span>  
  
|<span data-ttu-id="5015a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5015a-106">Member</span></span>|<span data-ttu-id="5015a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5015a-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="5015a-108">Enumera la caché de ensamblados precompilados con Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="5015a-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="5015a-109">Enumera la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5015a-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="5015a-110">Enumera los ensamblados que se han descargado a petición o que han sido instantáneas.</span><span class="sxs-lookup"><span data-stu-id="5015a-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="5015a-111">Indica que la [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) función debe devolver la ruta de acceso a la caché global de ensamblados de common language runtime (CLR) versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="5015a-111">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="5015a-112">Solo tiene sentido en el contexto de una llamada a [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="5015a-112">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="5015a-113">Indica que la [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) función debe devolver la ruta de acceso a la caché global de ensamblados para la versión 4 de CLR.</span><span class="sxs-lookup"><span data-stu-id="5015a-113">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="5015a-114">Solo tiene sentido en el contexto de una llamada a [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="5015a-114">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5015a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5015a-115">Requirements</span></span>  
 <span data-ttu-id="5015a-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5015a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5015a-117">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="5015a-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5015a-118">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5015a-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5015a-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5015a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5015a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5015a-120">See Also</span></span>  
 [<span data-ttu-id="5015a-121">GetCachePath (Función)</span><span class="sxs-lookup"><span data-stu-id="5015a-121">GetCachePath Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 [<span data-ttu-id="5015a-122">IAssemblyCacheItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5015a-122">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 [<span data-ttu-id="5015a-123">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="5015a-123">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
