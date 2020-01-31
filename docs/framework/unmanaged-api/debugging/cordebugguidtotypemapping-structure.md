---
title: CorDebugGuidToTypeMapping (estructura)
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
ms.openlocfilehash: b855a53c9e4303138d7605bdf108d37bb345b917
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789328"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="666c8-102">CorDebugGuidToTypeMapping (estructura)</span><span class="sxs-lookup"><span data-stu-id="666c8-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="666c8-103">Asigna un GUID de Windows Runtime a su objeto ICorDebugType correspondiente.</span><span class="sxs-lookup"><span data-stu-id="666c8-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="666c8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="666c8-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="666c8-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="666c8-105">Members</span></span>  
  
|<span data-ttu-id="666c8-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="666c8-106">Member</span></span>|<span data-ttu-id="666c8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="666c8-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="666c8-108">GUID del tipo de Windows Runtime almacenado en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="666c8-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="666c8-109">Un puntero a un objeto ICorDebugType que proporciona información sobre el tipo almacenado en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="666c8-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="666c8-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="666c8-110">Requirements</span></span>  
 <span data-ttu-id="666c8-111">**Plataformas:** Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="666c8-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="666c8-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="666c8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="666c8-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="666c8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="666c8-114">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="666c8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="666c8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="666c8-115">See also</span></span>

- [<span data-ttu-id="666c8-116">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="666c8-116">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="666c8-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="666c8-117">Debugging</span></span>](index.md)
