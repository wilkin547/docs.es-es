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
ms.openlocfilehash: b0625dc72d44485dbb69b42cba5387085d1862bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210430"
---
# <a name="stacktracesimplecontext-structure"></a><span data-ttu-id="0121d-102">StackTrace_SimpleContext (Estructura)</span><span class="sxs-lookup"><span data-stu-id="0121d-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="0121d-103">Proporciona un contexto simple que se puede usar en lugar de una estructura `CONTEXT` completa.</span><span class="sxs-lookup"><span data-stu-id="0121d-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0121d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0121d-104">Syntax</span></span>  
  
```  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="0121d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0121d-105">Members</span></span>  
  
|<span data-ttu-id="0121d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="0121d-106">Member</span></span>|<span data-ttu-id="0121d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0121d-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="0121d-108">El puntero de pila o el puntero de pila (ESP) en x86 plataformas.</span><span class="sxs-lookup"><span data-stu-id="0121d-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="0121d-109">Desplazamiento del marco o registro EBP en x86 plataformas.</span><span class="sxs-lookup"><span data-stu-id="0121d-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="0121d-110">El puntero de instrucción o el puntero de instrucción (EIP) en x86 plataformas.</span><span class="sxs-lookup"><span data-stu-id="0121d-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0121d-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0121d-111">Remarks</span></span>  
 <span data-ttu-id="0121d-112">Dado que las funciones de seguimiento de pila normalmente necesitan devolver la dirección, desplazamiento de trama y dirección de la pila, también puede usar el `SimpleContext` estructura en lugar de un gran `CONTEXT` estructura.</span><span class="sxs-lookup"><span data-stu-id="0121d-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0121d-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0121d-113">Requirements</span></span>  
 <span data-ttu-id="0121d-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0121d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0121d-115">**Encabezado**: SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="0121d-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 **<span data-ttu-id="0121d-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0121d-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0121d-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0121d-117">See also</span></span>

- [<span data-ttu-id="0121d-118">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="0121d-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="0121d-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="0121d-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
