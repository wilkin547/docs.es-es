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
ms.openlocfilehash: 1c94e03aa088d8f48eb7f7a418cebd0492319513
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696601"
---
# <a name="cordebuginternalframetype-enumeration"></a><span data-ttu-id="987bc-102">CorDebugInternalFrameType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="987bc-102">CorDebugInternalFrameType Enumeration</span></span>

<span data-ttu-id="987bc-103">Identifica el tipo de marco de pila.</span><span class="sxs-lookup"><span data-stu-id="987bc-103">Identifies the type of stack frame.</span></span> <span data-ttu-id="987bc-104">Esta enumeración la usa el método [ICorDebugInternalFrame (:: GetFrameType (](icordebuginternalframe-getframetype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="987bc-104">This enumeration is used by the [ICorDebugInternalFrame::GetFrameType](icordebuginternalframe-getframetype-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="987bc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="987bc-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="987bc-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="987bc-106">Members</span></span>  
  
|<span data-ttu-id="987bc-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="987bc-107">Member</span></span>|<span data-ttu-id="987bc-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="987bc-108">Description</span></span>|  
|------------|-----------------|  
|`STUBFRAME_NONE`|<span data-ttu-id="987bc-109">Un valor cero.</span><span class="sxs-lookup"><span data-stu-id="987bc-109">A null value.</span></span> <span data-ttu-id="987bc-110">El `ICorDebugInternalFrame::GetFrameType` método nunca devuelve este valor.</span><span class="sxs-lookup"><span data-stu-id="987bc-110">The `ICorDebugInternalFrame::GetFrameType` method never returns this value.</span></span>|  
|`STUBFRAME_M2U`|<span data-ttu-id="987bc-111">Marco de código auxiliar administrado a no administrado.</span><span class="sxs-lookup"><span data-stu-id="987bc-111">A managed-to-unmanaged stub frame.</span></span>|  
|`STUBFRAME_U2M`|<span data-ttu-id="987bc-112">Marco de código auxiliar no administrado que se administra.</span><span class="sxs-lookup"><span data-stu-id="987bc-112">An unmanaged-to-managed stub frame.</span></span>|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|<span data-ttu-id="987bc-113">Una transición entre dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="987bc-113">A transition between application domains.</span></span>|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|<span data-ttu-id="987bc-114">Llamada al método ligero.</span><span class="sxs-lookup"><span data-stu-id="987bc-114">A lightweight method call.</span></span>|  
|`STUBFRAME_FUNC_EVAL`|<span data-ttu-id="987bc-115">Inicio de la evaluación de la función.</span><span class="sxs-lookup"><span data-stu-id="987bc-115">The start of function evaluation.</span></span>|  
|`STUBFRAME_INTERNALCALL`|<span data-ttu-id="987bc-116">Una llamada interna en el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="987bc-116">An internal call into the common language runtime.</span></span>|  
|`STUBFRAME_CLASS_INIT`|<span data-ttu-id="987bc-117">Inicio de una inicialización de clase.</span><span class="sxs-lookup"><span data-stu-id="987bc-117">The start of a class initialization.</span></span>|  
|`STUBFRAME_EXCEPTION`|<span data-ttu-id="987bc-118">Excepción que se produce.</span><span class="sxs-lookup"><span data-stu-id="987bc-118">An exception that is thrown.</span></span>|  
|`STUBFRAME_SECURITY`|<span data-ttu-id="987bc-119">Marco que se usa para la seguridad de acceso del código.</span><span class="sxs-lookup"><span data-stu-id="987bc-119">A frame used for code access security.</span></span>|  
|`STUBFRAME_JIT_COMPILATION`|<span data-ttu-id="987bc-120">El tiempo de ejecución es una compilación JIT de un método.</span><span class="sxs-lookup"><span data-stu-id="987bc-120">The runtime is JIT-compiling a method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="987bc-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="987bc-121">Requirements</span></span>  

 <span data-ttu-id="987bc-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="987bc-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="987bc-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="987bc-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="987bc-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="987bc-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="987bc-125">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="987bc-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="987bc-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="987bc-126">See also</span></span>

- [<span data-ttu-id="987bc-127">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="987bc-127">Debugging Enumerations</span></span>](debugging-enumerations.md)
