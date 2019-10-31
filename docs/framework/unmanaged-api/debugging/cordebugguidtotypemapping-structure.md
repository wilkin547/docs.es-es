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
ms.openlocfilehash: 313f6649448653ad630d616c7dbf739653e352dc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132838"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="bab17-102">CorDebugGuidToTypeMapping (Estructura)</span><span class="sxs-lookup"><span data-stu-id="bab17-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="bab17-103">Asigna un GUID de Windows Runtime a su objeto ICorDebugType correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bab17-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bab17-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bab17-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="bab17-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="bab17-105">Members</span></span>  
  
|<span data-ttu-id="bab17-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="bab17-106">Member</span></span>|<span data-ttu-id="bab17-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bab17-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="bab17-108">GUID del tipo de Windows Runtime almacenado en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="bab17-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="bab17-109">Un puntero a un objeto ICorDebugType que proporciona información sobre el tipo almacenado en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="bab17-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bab17-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bab17-110">Requirements</span></span>  
 <span data-ttu-id="bab17-111">**Plataformas:** Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="bab17-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="bab17-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bab17-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bab17-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bab17-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bab17-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bab17-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bab17-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bab17-115">See also</span></span>

- [<span data-ttu-id="bab17-116">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="bab17-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="bab17-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="bab17-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
