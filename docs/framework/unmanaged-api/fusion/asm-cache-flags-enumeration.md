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
ms.openlocfilehash: 27caa9916b5adab2b2049a8f66ac34fed40e4d7f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778579"
---
# <a name="asmcacheflags-enumeration"></a><span data-ttu-id="67c03-102">ASM_CACHE_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="67c03-102">ASM_CACHE_FLAGS Enumeration</span></span>
<span data-ttu-id="67c03-103">Indica el origen de un ensamblado que se representa mediante [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="67c03-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c03-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67c03-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="67c03-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="67c03-105">Members</span></span>  
  
|<span data-ttu-id="67c03-106">Member</span><span class="sxs-lookup"><span data-stu-id="67c03-106">Member</span></span>|<span data-ttu-id="67c03-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="67c03-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="67c03-108">Enumera la caché de ensamblados precompilados mediante el uso de Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="67c03-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="67c03-109">Enumera la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="67c03-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="67c03-110">Enumera los ensamblados que se han descargado bajo demanda o que han sido copia sombra.</span><span class="sxs-lookup"><span data-stu-id="67c03-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="67c03-111">Indica que el [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) función debe devolver la ruta de acceso a la caché global de ensamblados de common language runtime (CLR) versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="67c03-111">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="67c03-112">Solo tiene sentido en el contexto de una llamada a [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="67c03-112">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="67c03-113">Indica que el [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) función debe devolver la ruta de acceso a la caché global de ensamblados para la versión 4 de CLR.</span><span class="sxs-lookup"><span data-stu-id="67c03-113">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="67c03-114">Solo tiene sentido en el contexto de una llamada a [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="67c03-114">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67c03-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67c03-115">Requirements</span></span>  
 <span data-ttu-id="67c03-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67c03-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67c03-117">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="67c03-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="67c03-118">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67c03-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="67c03-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67c03-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c03-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="67c03-120">See also</span></span>

- [<span data-ttu-id="67c03-121">GetCachePath (Función)</span><span class="sxs-lookup"><span data-stu-id="67c03-121">GetCachePath Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)
- [<span data-ttu-id="67c03-122">IAssemblyCacheItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="67c03-122">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
- [<span data-ttu-id="67c03-123">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="67c03-123">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
