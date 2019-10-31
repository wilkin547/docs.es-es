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
ms.openlocfilehash: cbc272070e9eb6810b34ec1f3fdc9e944c624cd3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132379"
---
# <a name="cor_active_function-structure"></a><span data-ttu-id="43c59-102">COR_ACTIVE_FUNCTION (Estructura)</span><span class="sxs-lookup"><span data-stu-id="43c59-102">COR_ACTIVE_FUNCTION Structure</span></span>
<span data-ttu-id="43c59-103">Contiene información sobre las funciones que están actualmente activas en los marcos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="43c59-103">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="43c59-104">El método [ICorDebugThread2:: GetActiveFunctions (](icordebugthread2-getactivefunctions-method.md) usa esta estructura.</span><span class="sxs-lookup"><span data-stu-id="43c59-104">This structure is used by the [ICorDebugThread2::GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c59-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43c59-105">Syntax</span></span>  
  
```cpp  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="43c59-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="43c59-106">Members</span></span>  
  
|<span data-ttu-id="43c59-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="43c59-107">Member</span></span>|<span data-ttu-id="43c59-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="43c59-108">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="43c59-109">Puntero al propietario del dominio de aplicación del campo `ilOffset`.</span><span class="sxs-lookup"><span data-stu-id="43c59-109">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="43c59-110">Puntero al propietario del módulo del campo `ilOffset`.</span><span class="sxs-lookup"><span data-stu-id="43c59-110">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="43c59-111">Puntero al propietario de la función del campo de `ilOffset`.</span><span class="sxs-lookup"><span data-stu-id="43c59-111">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="43c59-112">Desplazamiento del lenguaje intermedio de Microsoft (MSIL) del marco.</span><span class="sxs-lookup"><span data-stu-id="43c59-112">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="43c59-113">Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="43c59-113">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43c59-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43c59-114">Requirements</span></span>  
 <span data-ttu-id="43c59-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43c59-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43c59-116">**Encabezado:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="43c59-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="43c59-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43c59-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43c59-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43c59-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c59-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="43c59-119">See also</span></span>

- [<span data-ttu-id="43c59-120">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="43c59-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="43c59-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="43c59-121">Debugging</span></span>](index.md)
