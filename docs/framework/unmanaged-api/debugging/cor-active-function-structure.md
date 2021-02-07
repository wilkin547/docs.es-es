---
description: 'Más información acerca de: estructura de COR_ACTIVE_FUNCTION'
title: COR_ACTIVE_FUNCTION (Estructura)
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
ms.openlocfilehash: 7cc4a314c11ca4e2cdb4fe2b4090c471bcda26d5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747249"
---
# <a name="cor_active_function-structure"></a><span data-ttu-id="5239a-103">COR_ACTIVE_FUNCTION (Estructura)</span><span class="sxs-lookup"><span data-stu-id="5239a-103">COR_ACTIVE_FUNCTION Structure</span></span>

<span data-ttu-id="5239a-104">Contiene información sobre las funciones que están actualmente activas en los marcos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="5239a-104">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="5239a-105">El método [ICorDebugThread2:: GetActiveFunctions (](icordebugthread2-getactivefunctions-method.md) usa esta estructura.</span><span class="sxs-lookup"><span data-stu-id="5239a-105">This structure is used by the [ICorDebugThread2::GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5239a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5239a-106">Syntax</span></span>  
  
```cpp  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="5239a-107">Members</span><span class="sxs-lookup"><span data-stu-id="5239a-107">Members</span></span>  
  
|<span data-ttu-id="5239a-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="5239a-108">Member</span></span>|<span data-ttu-id="5239a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="5239a-109">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="5239a-110">Puntero al propietario del dominio de aplicación del `ilOffset` campo.</span><span class="sxs-lookup"><span data-stu-id="5239a-110">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="5239a-111">Puntero al propietario del módulo del `ilOffset` campo.</span><span class="sxs-lookup"><span data-stu-id="5239a-111">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="5239a-112">Puntero al propietario de la función del `ilOffset` campo.</span><span class="sxs-lookup"><span data-stu-id="5239a-112">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="5239a-113">Desplazamiento del lenguaje intermedio de Microsoft (MSIL) del marco.</span><span class="sxs-lookup"><span data-stu-id="5239a-113">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="5239a-114">Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="5239a-114">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5239a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5239a-115">Requirements</span></span>  

 <span data-ttu-id="5239a-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5239a-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5239a-117">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="5239a-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="5239a-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5239a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5239a-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5239a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5239a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5239a-120">See also</span></span>

- [<span data-ttu-id="5239a-121">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="5239a-121">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="5239a-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="5239a-122">Debugging</span></span>](index.md)
