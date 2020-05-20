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
ms.openlocfilehash: 45ae947cda5b4ddadfb10f5b2bdc78a95f031703
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420698"
---
# <a name="stacktrace_simplecontext-structure"></a><span data-ttu-id="fd242-102">StackTrace_SimpleContext (Estructura)</span><span class="sxs-lookup"><span data-stu-id="fd242-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="fd242-103">Proporciona un contexto simple que se puede usar en lugar de una estructura `CONTEXT` completa.</span><span class="sxs-lookup"><span data-stu-id="fd242-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd242-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd242-104">Syntax</span></span>  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="fd242-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="fd242-105">Members</span></span>  
  
|<span data-ttu-id="fd242-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="fd242-106">Member</span></span>|<span data-ttu-id="fd242-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd242-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="fd242-108">El puntero de pila o el puntero de pila Enter (ESP) en las plataformas x86.</span><span class="sxs-lookup"><span data-stu-id="fd242-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="fd242-109">El desplazamiento del marco o el registro EBP en las plataformas x86.</span><span class="sxs-lookup"><span data-stu-id="fd242-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="fd242-110">El puntero de instrucción o el puntero de instrucción Enter (EIP) en las plataformas x86.</span><span class="sxs-lookup"><span data-stu-id="fd242-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd242-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fd242-111">Remarks</span></span>  
 <span data-ttu-id="fd242-112">Dado que las funciones de seguimiento de pila normalmente solo necesitan devolver la dirección, el desplazamiento del marco y la dirección de la pila, también puede usar la `SimpleContext` estructura en lugar de una `CONTEXT` estructura grande.</span><span class="sxs-lookup"><span data-stu-id="fd242-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd242-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd242-113">Requirements</span></span>  
 <span data-ttu-id="fd242-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd242-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd242-115">**Encabezado:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="fd242-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="fd242-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd242-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd242-117">Consulta también</span><span class="sxs-lookup"><span data-stu-id="fd242-117">See also</span></span>

- [<span data-ttu-id="fd242-118">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="fd242-118">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="fd242-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="fd242-119">Debugging</span></span>](index.md)
