---
title: StackTrace_SimpleContext (Estructura)
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acf2ba752ace49ae288857dc22819a8e7e429a34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424058"
---
# <a name="stacktracesimplecontext-structure"></a><span data-ttu-id="9aabe-102">StackTrace_SimpleContext (Estructura)</span><span class="sxs-lookup"><span data-stu-id="9aabe-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="9aabe-103">Proporciona un contexto simple que se puede usar en lugar de una estructura `CONTEXT` completa.</span><span class="sxs-lookup"><span data-stu-id="9aabe-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aabe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9aabe-104">Syntax</span></span>  
  
```  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="9aabe-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9aabe-105">Members</span></span>  
  
|<span data-ttu-id="9aabe-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9aabe-106">Member</span></span>|<span data-ttu-id="9aabe-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9aabe-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="9aabe-108">El puntero de pila o puntero de pila (ESP) en x86 plataformas.</span><span class="sxs-lookup"><span data-stu-id="9aabe-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="9aabe-109">Desplazamiento del marco o registro EBP en x86 plataformas.</span><span class="sxs-lookup"><span data-stu-id="9aabe-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="9aabe-110">El puntero de instrucción o el puntero de instrucción (EIP) en x86 plataformas.</span><span class="sxs-lookup"><span data-stu-id="9aabe-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9aabe-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9aabe-111">Remarks</span></span>  
 <span data-ttu-id="9aabe-112">Dado que las funciones de seguimiento de pila normalmente se necesitan devolver sólo la dirección, el desplazamiento de marco y la dirección de la pila, puede utilizar opcionalmente la `SimpleContext` estructura en lugar de una gran `CONTEXT` estructura.</span><span class="sxs-lookup"><span data-stu-id="9aabe-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9aabe-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9aabe-113">Requirements</span></span>  
 <span data-ttu-id="9aabe-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9aabe-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9aabe-115">**Encabezado:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="9aabe-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="9aabe-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9aabe-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aabe-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9aabe-117">See Also</span></span>  
 [<span data-ttu-id="9aabe-118">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="9aabe-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="9aabe-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="9aabe-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
