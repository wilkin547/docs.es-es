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
ms.openlocfilehash: fe58a519d0feac0da49e7778247da1ef538f8b83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730037"
---
# <a name="malloc_type-enumeration"></a><span data-ttu-id="12c46-102">MALLOC_TYPE (enumeración)</span><span class="sxs-lookup"><span data-stu-id="12c46-102">MALLOC_TYPE Enumeration</span></span>

<span data-ttu-id="12c46-103">Contiene valores que especifican las características de la memoria que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="12c46-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12c46-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12c46-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="12c46-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="12c46-105">Members</span></span>  
  
|<span data-ttu-id="12c46-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="12c46-106">Member</span></span>|<span data-ttu-id="12c46-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="12c46-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="12c46-108">La memoria asignada puede contener un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="12c46-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="12c46-109">La memoria asignada es segura para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="12c46-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="12c46-110">Es decir, se puede tener acceso a la memoria por parte de varios subprocesos sin ninguna sincronización.</span><span class="sxs-lookup"><span data-stu-id="12c46-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="12c46-111">Si no se establece esta marca, se deben serializar las llamadas en el objeto.</span><span class="sxs-lookup"><span data-stu-id="12c46-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="12c46-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="12c46-112">Requirements</span></span>  

 <span data-ttu-id="12c46-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12c46-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12c46-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="12c46-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="12c46-115">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="12c46-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12c46-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12c46-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c46-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12c46-117">See also</span></span>

- [<span data-ttu-id="12c46-118">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="12c46-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
