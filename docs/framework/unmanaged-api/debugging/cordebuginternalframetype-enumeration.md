---
title: CorDebugInternalFrameType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugInternalFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInternalFrameType
helpviewer_keywords:
- CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05184ceb3b32eb003951fff5cfdfbfb813992552
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216059"
---
# <a name="cordebuginternalframetype-enumeration"></a><span data-ttu-id="a9f19-102">CorDebugInternalFrameType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a9f19-102">CorDebugInternalFrameType Enumeration</span></span>
<span data-ttu-id="a9f19-103">Identifica el tipo de marco de pila.</span><span class="sxs-lookup"><span data-stu-id="a9f19-103">Identifies the type of stack frame.</span></span> <span data-ttu-id="a9f19-104">Esta enumeración se utiliza en el [ICorDebugInternalFrame:: GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="a9f19-104">This enumeration is used by the [ICorDebugInternalFrame::GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9f19-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9f19-105">Syntax</span></span>  
  
```  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a><span data-ttu-id="a9f19-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="a9f19-106">Members</span></span>  
  
|<span data-ttu-id="a9f19-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="a9f19-107">Member</span></span>|<span data-ttu-id="a9f19-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9f19-108">Description</span></span>|  
|------------|-----------------|  
|`STUBFRAME_NONE`|<span data-ttu-id="a9f19-109">Un valor cero.</span><span class="sxs-lookup"><span data-stu-id="a9f19-109">A null value.</span></span> <span data-ttu-id="a9f19-110">El `ICorDebugInternalFrame::GetFrameType` método nunca devuelve este valor.</span><span class="sxs-lookup"><span data-stu-id="a9f19-110">The `ICorDebugInternalFrame::GetFrameType` method never returns this value.</span></span>|  
|`STUBFRAME_M2U`|<span data-ttu-id="a9f19-111">Un marco de código auxiliar a administrado.</span><span class="sxs-lookup"><span data-stu-id="a9f19-111">A managed-to-unmanaged stub frame.</span></span>|  
|`STUBFRAME_U2M`|<span data-ttu-id="a9f19-112">Un marco de código auxiliar no administrado a administrado.</span><span class="sxs-lookup"><span data-stu-id="a9f19-112">An unmanaged-to-managed stub frame.</span></span>|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|<span data-ttu-id="a9f19-113">Una transición entre los dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9f19-113">A transition between application domains.</span></span>|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|<span data-ttu-id="a9f19-114">Una llamada de método ligero.</span><span class="sxs-lookup"><span data-stu-id="a9f19-114">A lightweight method call.</span></span>|  
|`STUBFRAME_FUNC_EVAL`|<span data-ttu-id="a9f19-115">Inicio de la evaluación de función.</span><span class="sxs-lookup"><span data-stu-id="a9f19-115">The start of function evaluation.</span></span>|  
|`STUBFRAME_INTERNALCALL`|<span data-ttu-id="a9f19-116">Una llamada interna en common language runtime.</span><span class="sxs-lookup"><span data-stu-id="a9f19-116">An internal call into the common language runtime.</span></span>|  
|`STUBFRAME_CLASS_INIT`|<span data-ttu-id="a9f19-117">Inicio de la inicialización de una clase.</span><span class="sxs-lookup"><span data-stu-id="a9f19-117">The start of a class initialization.</span></span>|  
|`STUBFRAME_EXCEPTION`|<span data-ttu-id="a9f19-118">Una excepción que se produce.</span><span class="sxs-lookup"><span data-stu-id="a9f19-118">An exception that is thrown.</span></span>|  
|`STUBFRAME_SECURITY`|<span data-ttu-id="a9f19-119">Un marco que se usa para la seguridad de acceso del código.</span><span class="sxs-lookup"><span data-stu-id="a9f19-119">A frame used for code access security.</span></span>|  
|`STUBFRAME_JIT_COMPILATION`|<span data-ttu-id="a9f19-120">El tiempo de ejecución es un método de compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="a9f19-120">The runtime is JIT-compiling a method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9f19-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9f19-121">Requirements</span></span>  
 <span data-ttu-id="a9f19-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9f19-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9f19-123">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9f19-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9f19-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9f19-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9f19-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9f19-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9f19-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9f19-126">See also</span></span>

- [<span data-ttu-id="a9f19-127">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="a9f19-127">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
