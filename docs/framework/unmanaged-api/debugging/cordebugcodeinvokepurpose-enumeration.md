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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79730bb98a7e2d84517ed068a52614ad8650f541
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406226"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a><span data-ttu-id="378b7-102">Enumeración CorDebugCodeInvokePurpose</span><span class="sxs-lookup"><span data-stu-id="378b7-102">CorDebugCodeInvokePurpose Enumeration</span></span>
<span data-ttu-id="378b7-103">Explica los motivos por los que una función exportada llama a código administrado.</span><span class="sxs-lookup"><span data-stu-id="378b7-103">Describes why an exported function calls managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="378b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="378b7-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a><span data-ttu-id="378b7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="378b7-105">Members</span></span>  
  
|<span data-ttu-id="378b7-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="378b7-106">Member</span></span>|<span data-ttu-id="378b7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="378b7-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|<span data-ttu-id="378b7-108">Ninguno o desconocido.</span><span class="sxs-lookup"><span data-stu-id="378b7-108">None or unknown.</span></span>|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|<span data-ttu-id="378b7-109">El código administrado ejecutará cualquier punto de entrada administrado, como una PInvoke inversa.</span><span class="sxs-lookup"><span data-stu-id="378b7-109">The managed code will run any managed entry point, such as a reverse p-invoke.</span></span> <span data-ttu-id="378b7-110">Cualquier otro propósito más detallado es desconocido para el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="378b7-110">Any more detailed purpose is unknown by the runtime.</span></span>|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|<span data-ttu-id="378b7-111">El código administrado ejecutará un constructor estático.</span><span class="sxs-lookup"><span data-stu-id="378b7-111">The managed code will run a static constructor.</span></span>|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|<span data-ttu-id="378b7-112">El código administrado ejecutará la implementación de un método de interfaz que se haya llamado.</span><span class="sxs-lookup"><span data-stu-id="378b7-112">The managed code will run the implementation for some interface method that was called.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="378b7-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="378b7-113">Remarks</span></span>  
 <span data-ttu-id="378b7-114">Esta enumeración se usa en la [icordebugprocess6:: Getexportstepinfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) método para proporcionar información acerca de la ejecución paso a paso el código administrado.</span><span class="sxs-lookup"><span data-stu-id="378b7-114">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="378b7-115">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="378b7-115">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="378b7-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="378b7-116">Requirements</span></span>  
 <span data-ttu-id="378b7-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="378b7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="378b7-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="378b7-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="378b7-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="378b7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="378b7-120">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="378b7-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="378b7-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="378b7-121">See Also</span></span>  
 [<span data-ttu-id="378b7-122">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="378b7-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="378b7-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="378b7-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
