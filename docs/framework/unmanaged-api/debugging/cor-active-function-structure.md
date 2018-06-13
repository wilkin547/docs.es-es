---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86ab3d3a0f460f1ecdf86147b14df205aaf49635
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404205"
---
# <a name="coractivefunction-structure"></a><span data-ttu-id="99027-102">COR_ACTIVE_FUNCTION (Estructura)</span><span class="sxs-lookup"><span data-stu-id="99027-102">COR_ACTIVE_FUNCTION Structure</span></span>
<span data-ttu-id="99027-103">Contiene información sobre las funciones que están actualmente activas en los marcos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="99027-103">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="99027-104">Esta estructura se usa por la [ICorDebugThread2:: GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="99027-104">This structure is used by the [ICorDebugThread2::GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99027-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99027-105">Syntax</span></span>  
  
```  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="99027-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="99027-106">Members</span></span>  
  
|<span data-ttu-id="99027-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="99027-107">Member</span></span>|<span data-ttu-id="99027-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="99027-108">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="99027-109">Puntero para el propietario del dominio de aplicación de la `ilOffset` campo.</span><span class="sxs-lookup"><span data-stu-id="99027-109">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="99027-110">Puntero al propietario del módulo de la `ilOffset` campo.</span><span class="sxs-lookup"><span data-stu-id="99027-110">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="99027-111">Puntero al propietario de la función de la `ilOffset` campo.</span><span class="sxs-lookup"><span data-stu-id="99027-111">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="99027-112">El desplazamiento de lenguaje intermedio (MSIL) de Microsoft del marco.</span><span class="sxs-lookup"><span data-stu-id="99027-112">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="99027-113">Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="99027-113">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99027-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99027-114">Requirements</span></span>  
 <span data-ttu-id="99027-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99027-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99027-116">**Encabezado:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="99027-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="99027-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99027-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99027-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99027-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99027-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="99027-119">See Also</span></span>  
 [<span data-ttu-id="99027-120">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="99027-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="99027-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="99027-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
