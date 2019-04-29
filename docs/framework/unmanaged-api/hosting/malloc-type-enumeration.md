---
title: MALLOC_TYPE (enumeración)
ms.date: 03/30/2017
api_name:
- MALLOC_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MALLOC_TYPE
helpviewer_keywords:
- MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 695f69c8d9c3a295a705971743733339cf8aab13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765224"
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="879be-102">MALLOC_TYPE (enumeración)</span><span class="sxs-lookup"><span data-stu-id="879be-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="879be-103">Contiene valores que especifican las características de la memoria que se está asignando.</span><span class="sxs-lookup"><span data-stu-id="879be-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="879be-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="879be-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="879be-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="879be-105">Members</span></span>  
  
|<span data-ttu-id="879be-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="879be-106">Member</span></span>|<span data-ttu-id="879be-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="879be-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="879be-108">La memoria asignada puede contener un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="879be-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="879be-109">La memoria asignada es segura para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="879be-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="879be-110">Es decir, la memoria puede obtenerse mediante varios subprocesos sin ninguna sincronización.</span><span class="sxs-lookup"><span data-stu-id="879be-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="879be-111">Si no se establece esta marca, se deben serializar las llamadas en el objeto.</span><span class="sxs-lookup"><span data-stu-id="879be-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="879be-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="879be-112">Requirements</span></span>  
 <span data-ttu-id="879be-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="879be-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="879be-114">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="879be-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="879be-115">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="879be-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="879be-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="879be-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="879be-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="879be-117">See also</span></span>

- [<span data-ttu-id="879be-118">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="879be-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
