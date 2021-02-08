---
description: 'Más información sobre: enumeración CorDebugCodeInvokePurpose'
title: Enumeración CorDebugCodeInvokePurpose
ms.date: 03/30/2017
api_name:
- CorDebugInvokePurpose
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type:
- apiref
ms.openlocfilehash: 1402343cc15e451975567564e6ce353900454bf4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801727"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a><span data-ttu-id="06b58-103">Enumeración CorDebugCodeInvokePurpose</span><span class="sxs-lookup"><span data-stu-id="06b58-103">CorDebugCodeInvokePurpose Enumeration</span></span>

<span data-ttu-id="06b58-104">Explica los motivos por los que una función exportada llama a código administrado.</span><span class="sxs-lookup"><span data-stu-id="06b58-104">Describes why an exported function calls managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06b58-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06b58-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a><span data-ttu-id="06b58-106">Members</span><span class="sxs-lookup"><span data-stu-id="06b58-106">Members</span></span>  
  
|<span data-ttu-id="06b58-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="06b58-107">Member</span></span>|<span data-ttu-id="06b58-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="06b58-108">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|<span data-ttu-id="06b58-109">Ninguno o desconocido.</span><span class="sxs-lookup"><span data-stu-id="06b58-109">None or unknown.</span></span>|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|<span data-ttu-id="06b58-110">El código administrado ejecutará cualquier punto de entrada administrado, como una PInvoke inversa.</span><span class="sxs-lookup"><span data-stu-id="06b58-110">The managed code will run any managed entry point, such as a reverse p-invoke.</span></span> <span data-ttu-id="06b58-111">Cualquier otro propósito más detallado es desconocido para el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="06b58-111">Any more detailed purpose is unknown by the runtime.</span></span>|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|<span data-ttu-id="06b58-112">El código administrado ejecutará un constructor estático.</span><span class="sxs-lookup"><span data-stu-id="06b58-112">The managed code will run a static constructor.</span></span>|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|<span data-ttu-id="06b58-113">El código administrado ejecutará la implementación de un método de interfaz que se haya llamado.</span><span class="sxs-lookup"><span data-stu-id="06b58-113">The managed code will run the implementation for some interface method that was called.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06b58-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="06b58-114">Remarks</span></span>  

 <span data-ttu-id="06b58-115">El método [método icordebugprocess6:: GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) usa esta enumeración para proporcionar información sobre la ejecución paso a paso a través del código administrado.</span><span class="sxs-lookup"><span data-stu-id="06b58-115">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="06b58-116">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="06b58-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06b58-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06b58-117">Requirements</span></span>  

 <span data-ttu-id="06b58-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06b58-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06b58-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06b58-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06b58-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06b58-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06b58-121">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06b58-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b58-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="06b58-122">See also</span></span>

- [<span data-ttu-id="06b58-123">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="06b58-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="06b58-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="06b58-124">Debugging</span></span>](index.md)
