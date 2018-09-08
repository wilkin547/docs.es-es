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
ms.openlocfilehash: 5b712c6ae5978e83dab085f48dd1fd572757384a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44197765"
---
# <a name="asmcacheflags-enumeration"></a><span data-ttu-id="08ff9-102">ASM_CACHE_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="08ff9-102">ASM_CACHE_FLAGS Enumeration</span></span>
<span data-ttu-id="08ff9-103">Indica el origen de un ensamblado que se representa mediante [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="08ff9-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08ff9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08ff9-104">Syntax</span></span>  
  
```  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="08ff9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="08ff9-105">Members</span></span>  
  
|<span data-ttu-id="08ff9-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="08ff9-106">Member</span></span>|<span data-ttu-id="08ff9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="08ff9-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="08ff9-108">Enumera la caché de ensamblados precompilados mediante el uso de Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="08ff9-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="08ff9-109">Enumera la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="08ff9-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="08ff9-110">Enumera los ensamblados que se han descargado bajo demanda o que han sido copia sombra.</span><span class="sxs-lookup"><span data-stu-id="08ff9-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="08ff9-111">Indica que el [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) función debe devolver la ruta de acceso a la caché global de ensamblados de common language runtime (CLR) versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="08ff9-111">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="08ff9-112">Solo tiene sentido en el contexto de una llamada a [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="08ff9-112">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="08ff9-113">Indica que el [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) función debe devolver la ruta de acceso a la caché global de ensamblados para la versión 4 de CLR.</span><span class="sxs-lookup"><span data-stu-id="08ff9-113">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="08ff9-114">Solo tiene sentido en el contexto de una llamada a [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="08ff9-114">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="08ff9-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08ff9-115">Requirements</span></span>  
 <span data-ttu-id="08ff9-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08ff9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08ff9-117">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="08ff9-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="08ff9-118">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08ff9-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08ff9-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08ff9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08ff9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="08ff9-120">See Also</span></span>  
 [<span data-ttu-id="08ff9-121">GetCachePath (Función)</span><span class="sxs-lookup"><span data-stu-id="08ff9-121">GetCachePath Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 [<span data-ttu-id="08ff9-122">IAssemblyCacheItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="08ff9-122">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 [<span data-ttu-id="08ff9-123">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="08ff9-123">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
