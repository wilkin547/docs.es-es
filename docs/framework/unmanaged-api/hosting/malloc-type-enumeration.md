---
description: 'Más información acerca de: enumeración MALLOC_TYPE'
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
ms.openlocfilehash: 47eb58107d79309c34af5f0acdf614804d1f208f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679810"
---
# <a name="malloc_type-enumeration"></a><span data-ttu-id="ad181-103">MALLOC_TYPE (enumeración)</span><span class="sxs-lookup"><span data-stu-id="ad181-103">MALLOC_TYPE Enumeration</span></span>

<span data-ttu-id="ad181-104">Contiene valores que especifican las características de la memoria que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="ad181-104">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad181-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad181-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="ad181-106">Members</span><span class="sxs-lookup"><span data-stu-id="ad181-106">Members</span></span>  
  
|<span data-ttu-id="ad181-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="ad181-107">Member</span></span>|<span data-ttu-id="ad181-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad181-108">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="ad181-109">La memoria asignada puede contener un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="ad181-109">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="ad181-110">La memoria asignada es segura para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ad181-110">The allocated memory is thread-safe.</span></span> <span data-ttu-id="ad181-111">Es decir, se puede tener acceso a la memoria por parte de varios subprocesos sin ninguna sincronización.</span><span class="sxs-lookup"><span data-stu-id="ad181-111">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="ad181-112">Si no se establece esta marca, se deben serializar las llamadas en el objeto.</span><span class="sxs-lookup"><span data-stu-id="ad181-112">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ad181-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad181-113">Requirements</span></span>  

 <span data-ttu-id="ad181-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad181-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad181-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ad181-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ad181-116">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ad181-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad181-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad181-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad181-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad181-118">See also</span></span>

- [<span data-ttu-id="ad181-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="ad181-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
