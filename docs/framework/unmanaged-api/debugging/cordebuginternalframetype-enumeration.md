---
description: 'Más información sobre: enumeración CorDebugInternalFrameType ('
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
ms.openlocfilehash: 0479ae7602224e03086b9dacf91d360253b61818
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662005"
---
# <a name="cordebuginternalframetype-enumeration"></a><span data-ttu-id="a09a2-103">CorDebugInternalFrameType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a09a2-103">CorDebugInternalFrameType Enumeration</span></span>

<span data-ttu-id="a09a2-104">Identifica el tipo de marco de pila.</span><span class="sxs-lookup"><span data-stu-id="a09a2-104">Identifies the type of stack frame.</span></span> <span data-ttu-id="a09a2-105">Esta enumeración la usa el método [ICorDebugInternalFrame (:: GetFrameType (](icordebuginternalframe-getframetype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a09a2-105">This enumeration is used by the [ICorDebugInternalFrame::GetFrameType](icordebuginternalframe-getframetype-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a09a2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a09a2-106">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="a09a2-107">Members</span><span class="sxs-lookup"><span data-stu-id="a09a2-107">Members</span></span>  
  
|<span data-ttu-id="a09a2-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="a09a2-108">Member</span></span>|<span data-ttu-id="a09a2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a09a2-109">Description</span></span>|  
|------------|-----------------|  
|`STUBFRAME_NONE`|<span data-ttu-id="a09a2-110">Un valor cero.</span><span class="sxs-lookup"><span data-stu-id="a09a2-110">A null value.</span></span> <span data-ttu-id="a09a2-111">El `ICorDebugInternalFrame::GetFrameType` método nunca devuelve este valor.</span><span class="sxs-lookup"><span data-stu-id="a09a2-111">The `ICorDebugInternalFrame::GetFrameType` method never returns this value.</span></span>|  
|`STUBFRAME_M2U`|<span data-ttu-id="a09a2-112">Marco de código auxiliar administrado a no administrado.</span><span class="sxs-lookup"><span data-stu-id="a09a2-112">A managed-to-unmanaged stub frame.</span></span>|  
|`STUBFRAME_U2M`|<span data-ttu-id="a09a2-113">Marco de código auxiliar no administrado que se administra.</span><span class="sxs-lookup"><span data-stu-id="a09a2-113">An unmanaged-to-managed stub frame.</span></span>|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|<span data-ttu-id="a09a2-114">Una transición entre dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a09a2-114">A transition between application domains.</span></span>|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|<span data-ttu-id="a09a2-115">Llamada al método ligero.</span><span class="sxs-lookup"><span data-stu-id="a09a2-115">A lightweight method call.</span></span>|  
|`STUBFRAME_FUNC_EVAL`|<span data-ttu-id="a09a2-116">Inicio de la evaluación de la función.</span><span class="sxs-lookup"><span data-stu-id="a09a2-116">The start of function evaluation.</span></span>|  
|`STUBFRAME_INTERNALCALL`|<span data-ttu-id="a09a2-117">Una llamada interna en el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a09a2-117">An internal call into the common language runtime.</span></span>|  
|`STUBFRAME_CLASS_INIT`|<span data-ttu-id="a09a2-118">Inicio de una inicialización de clase.</span><span class="sxs-lookup"><span data-stu-id="a09a2-118">The start of a class initialization.</span></span>|  
|`STUBFRAME_EXCEPTION`|<span data-ttu-id="a09a2-119">Excepción que se produce.</span><span class="sxs-lookup"><span data-stu-id="a09a2-119">An exception that is thrown.</span></span>|  
|`STUBFRAME_SECURITY`|<span data-ttu-id="a09a2-120">Marco que se usa para la seguridad de acceso del código.</span><span class="sxs-lookup"><span data-stu-id="a09a2-120">A frame used for code access security.</span></span>|  
|`STUBFRAME_JIT_COMPILATION`|<span data-ttu-id="a09a2-121">El tiempo de ejecución es una compilación JIT de un método.</span><span class="sxs-lookup"><span data-stu-id="a09a2-121">The runtime is JIT-compiling a method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a09a2-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a09a2-122">Requirements</span></span>  

 <span data-ttu-id="a09a2-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a09a2-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a09a2-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a09a2-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a09a2-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a09a2-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a09a2-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a09a2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a09a2-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="a09a2-127">See also</span></span>

- [<span data-ttu-id="a09a2-128">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="a09a2-128">Debugging Enumerations</span></span>](debugging-enumerations.md)
