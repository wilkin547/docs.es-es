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
ms.openlocfilehash: 49290a37ca7ea101e3c8b458a5daa4995cb3beee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610050"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="d634a-102">CorDebugGuidToTypeMapping (Estructura)</span><span class="sxs-lookup"><span data-stu-id="d634a-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="d634a-103">Se asigna un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID a su objeto ICorDebugType correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d634a-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d634a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d634a-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="d634a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d634a-105">Members</span></span>  
  
|<span data-ttu-id="d634a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="d634a-106">Member</span></span>|<span data-ttu-id="d634a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d634a-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="d634a-108">El GUID de la caché [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo.</span><span class="sxs-lookup"><span data-stu-id="d634a-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="d634a-109">Un puntero a un objeto ICorDebugType que proporciona información sobre el tipo almacenado en caché.</span><span class="sxs-lookup"><span data-stu-id="d634a-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d634a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d634a-110">Requirements</span></span>  
 <span data-ttu-id="d634a-111">**Plataformas:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d634a-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="d634a-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d634a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d634a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d634a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d634a-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d634a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d634a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d634a-115">See also</span></span>
- [<span data-ttu-id="d634a-116">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="d634a-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="d634a-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="d634a-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
