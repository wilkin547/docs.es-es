---
title: CorDebugGuidToTypeMapping (Estructura)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38e1b19d6340f559e6f8b7e0f7bc042a10df16c3
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025988"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="8e127-102">CorDebugGuidToTypeMapping (Estructura)</span><span class="sxs-lookup"><span data-stu-id="8e127-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="8e127-103">Asigna un GUID en tiempo de ejecución de Windows a su objeto ICorDebugType correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8e127-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e127-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e127-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="8e127-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8e127-105">Members</span></span>  
  
|<span data-ttu-id="8e127-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="8e127-106">Member</span></span>|<span data-ttu-id="8e127-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e127-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="8e127-108">El GUID del tipo en tiempo de ejecución de Windows almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="8e127-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="8e127-109">Un puntero a un objeto ICorDebugType que proporciona información sobre el tipo almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="8e127-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8e127-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e127-110">Requirements</span></span>  
 <span data-ttu-id="8e127-111">**Plataformas:** En tiempo de ejecución de Windows.</span><span class="sxs-lookup"><span data-stu-id="8e127-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="8e127-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e127-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e127-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e127-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e127-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e127-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e127-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e127-115">See also</span></span>

- [<span data-ttu-id="8e127-116">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="8e127-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="8e127-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="8e127-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
