---
description: 'Más información acerca de: estructura Cordebugguidtotypemapping ('
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
ms.openlocfilehash: 5f6e99a17483b4fc16eb36ebb5fb5fd81380944b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801623"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="328e1-103">CorDebugGuidToTypeMapping (Estructura)</span><span class="sxs-lookup"><span data-stu-id="328e1-103">CorDebugGuidToTypeMapping Structure</span></span>

<span data-ttu-id="328e1-104">Asigna un GUID de Windows Runtime a su objeto ICorDebugType correspondiente.</span><span class="sxs-lookup"><span data-stu-id="328e1-104">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="328e1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="328e1-105">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="328e1-106">Members</span><span class="sxs-lookup"><span data-stu-id="328e1-106">Members</span></span>  
  
|<span data-ttu-id="328e1-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="328e1-107">Member</span></span>|<span data-ttu-id="328e1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="328e1-108">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="328e1-109">GUID del tipo de Windows Runtime almacenado en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="328e1-109">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="328e1-110">Un puntero a un objeto ICorDebugType que proporciona información sobre el tipo almacenado en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="328e1-110">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="328e1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="328e1-111">Requirements</span></span>  

 <span data-ttu-id="328e1-112">**Plataformas:** Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="328e1-112">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="328e1-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="328e1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="328e1-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="328e1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="328e1-115">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="328e1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="328e1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="328e1-116">See also</span></span>

- [<span data-ttu-id="328e1-117">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="328e1-117">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="328e1-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="328e1-118">Debugging</span></span>](index.md)
