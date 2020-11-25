---
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
ms.openlocfilehash: cb65663ec1c1562009d0281c2e176b628b6366b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732182"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a><span data-ttu-id="a3502-102">Enumeración CorDebugCodeInvokePurpose</span><span class="sxs-lookup"><span data-stu-id="a3502-102">CorDebugCodeInvokePurpose Enumeration</span></span>

<span data-ttu-id="a3502-103">Explica los motivos por los que una función exportada llama a código administrado.</span><span class="sxs-lookup"><span data-stu-id="a3502-103">Describes why an exported function calls managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3502-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3502-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a><span data-ttu-id="a3502-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a3502-105">Members</span></span>  
  
|<span data-ttu-id="a3502-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a3502-106">Member</span></span>|<span data-ttu-id="a3502-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3502-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|<span data-ttu-id="a3502-108">Ninguno o desconocido.</span><span class="sxs-lookup"><span data-stu-id="a3502-108">None or unknown.</span></span>|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|<span data-ttu-id="a3502-109">El código administrado ejecutará cualquier punto de entrada administrado, como una PInvoke inversa.</span><span class="sxs-lookup"><span data-stu-id="a3502-109">The managed code will run any managed entry point, such as a reverse p-invoke.</span></span> <span data-ttu-id="a3502-110">Cualquier otro propósito más detallado es desconocido para el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a3502-110">Any more detailed purpose is unknown by the runtime.</span></span>|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|<span data-ttu-id="a3502-111">El código administrado ejecutará un constructor estático.</span><span class="sxs-lookup"><span data-stu-id="a3502-111">The managed code will run a static constructor.</span></span>|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|<span data-ttu-id="a3502-112">El código administrado ejecutará la implementación de un método de interfaz que se haya llamado.</span><span class="sxs-lookup"><span data-stu-id="a3502-112">The managed code will run the implementation for some interface method that was called.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3502-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a3502-113">Remarks</span></span>  

 <span data-ttu-id="a3502-114">El método [método icordebugprocess6:: GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) usa esta enumeración para proporcionar información sobre la ejecución paso a paso a través del código administrado.</span><span class="sxs-lookup"><span data-stu-id="a3502-114">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3502-115">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a3502-115">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3502-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3502-116">Requirements</span></span>  

 <span data-ttu-id="a3502-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3502-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3502-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3502-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3502-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3502-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3502-120">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3502-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3502-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3502-121">See also</span></span>

- [<span data-ttu-id="a3502-122">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="a3502-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="a3502-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="a3502-123">Debugging</span></span>](index.md)
