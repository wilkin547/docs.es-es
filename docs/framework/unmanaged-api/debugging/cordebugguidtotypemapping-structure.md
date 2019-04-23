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
ms.openlocfilehash: 9dc7093edaf12e801a1e1adc52b0be823ff92b91
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079921"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="930b2-102">CorDebugGuidToTypeMapping (Estructura)</span><span class="sxs-lookup"><span data-stu-id="930b2-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="930b2-103">Se asigna un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID a su objeto ICorDebugType correspondiente.</span><span class="sxs-lookup"><span data-stu-id="930b2-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="930b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="930b2-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="930b2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="930b2-105">Members</span></span>  
  
|<span data-ttu-id="930b2-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="930b2-106">Member</span></span>|<span data-ttu-id="930b2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="930b2-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="930b2-108">El GUID de la caché [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo.</span><span class="sxs-lookup"><span data-stu-id="930b2-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="930b2-109">Un puntero a un objeto ICorDebugType que proporciona información sobre el tipo almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="930b2-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="930b2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="930b2-110">Requirements</span></span>  
 <span data-ttu-id="930b2-111">**Plataformas:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="930b2-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="930b2-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="930b2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="930b2-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="930b2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="930b2-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="930b2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="930b2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="930b2-115">See also</span></span>

- [<span data-ttu-id="930b2-116">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="930b2-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="930b2-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="930b2-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
