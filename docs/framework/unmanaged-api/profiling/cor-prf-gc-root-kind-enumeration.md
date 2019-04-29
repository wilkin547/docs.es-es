---
title: COR_PRF_GC_ROOT_KIND (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_KIND
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_KIND
helpviewer_keywords:
- COR_PRF_GC_ROOT_KIND enumeration [.NET Framework profiling]
ms.assetid: b9fb1c03-417f-41d4-aed4-02cb4ade8def
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7dfbba3cef8afadfc6e12e53ea328c4fc7165ca0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599361"
---
# <a name="corprfgcrootkind-enumeration"></a><span data-ttu-id="714d0-102">COR_PRF_GC_ROOT_KIND (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="714d0-102">COR_PRF_GC_ROOT_KIND Enumeration</span></span>
<span data-ttu-id="714d0-103">Indica el tipo de raíz de la colección de elementos no utilizados que se expone mediante el [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="714d0-103">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="714d0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="714d0-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="714d0-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="714d0-105">Members</span></span>  
  
|<span data-ttu-id="714d0-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="714d0-106">Member</span></span>|<span data-ttu-id="714d0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="714d0-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="714d0-108">La raíz es una variable en la pila.</span><span class="sxs-lookup"><span data-stu-id="714d0-108">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="714d0-109">La raíz es una entrada en la cola del finalizador.</span><span class="sxs-lookup"><span data-stu-id="714d0-109">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="714d0-110">La raíz es un identificador de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="714d0-110">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="714d0-111">El tipo de raíz no está especificado.</span><span class="sxs-lookup"><span data-stu-id="714d0-111">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="714d0-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="714d0-112">Requirements</span></span>  
 <span data-ttu-id="714d0-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="714d0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="714d0-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="714d0-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="714d0-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="714d0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="714d0-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="714d0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="714d0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="714d0-117">See also</span></span>

- [<span data-ttu-id="714d0-118">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="714d0-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
