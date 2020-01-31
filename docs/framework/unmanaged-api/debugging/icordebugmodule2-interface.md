---
title: Interfaz ICorDebugModule2
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
ms.openlocfilehash: 32774aacecf3e56510bc6f0670538a44fde794c9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792985"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="bf4c2-102">Interfaz ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="bf4c2-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="bf4c2-103">Actúa como una extensión lógica de la interfaz ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="bf4c2-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf4c2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="bf4c2-104">Methods</span></span>  
  
|<span data-ttu-id="bf4c2-105">Método</span><span class="sxs-lookup"><span data-stu-id="bf4c2-105">Method</span></span>|<span data-ttu-id="bf4c2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf4c2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf4c2-107">ApplyChanges (método)</span><span class="sxs-lookup"><span data-stu-id="bf4c2-107">ApplyChanges Method</span></span>](icordebugmodule2-applychanges-method.md)|<span data-ttu-id="bf4c2-108">Aplica los cambios en los metadatos y los cambios en el código del lenguaje intermedio de Microsoft (MSIL) al proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="bf4c2-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="bf4c2-109">GetJITCompilerFlags (método)</span><span class="sxs-lookup"><span data-stu-id="bf4c2-109">GetJITCompilerFlags Method</span></span>](icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="bf4c2-110">Obtiene las marcas que controlan la compilación Just-in-Time (JIT) para esta `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="bf4c2-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="bf4c2-111">ResolveAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="bf4c2-111">ResolveAssembly Method</span></span>](icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="bf4c2-112">Resuelve el ensamblado al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="bf4c2-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="bf4c2-113">SetJITCompilerFlags (método)</span><span class="sxs-lookup"><span data-stu-id="bf4c2-113">SetJITCompilerFlags Method</span></span>](icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="bf4c2-114">Establece las marcas que controlan la compilación JIT para esta `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="bf4c2-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="bf4c2-115">SetJMCStatus (método)</span><span class="sxs-lookup"><span data-stu-id="bf4c2-115">SetJMCStatus Method</span></span>](icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="bf4c2-116">Establece el Estado Solo mi código (JMC) de todos los métodos de todas las clases de este `ICorDebugModule2` en el valor especificado, excepto en los de la matriz `pTokens`, que establece en el valor opuesto.</span><span class="sxs-lookup"><span data-stu-id="bf4c2-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf4c2-117">Notas</span><span class="sxs-lookup"><span data-stu-id="bf4c2-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf4c2-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="bf4c2-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf4c2-119">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="bf4c2-119">Requirements</span></span>  
 <span data-ttu-id="bf4c2-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf4c2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf4c2-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf4c2-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf4c2-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf4c2-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf4c2-123">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf4c2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf4c2-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf4c2-124">See also</span></span>

- [<span data-ttu-id="bf4c2-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="bf4c2-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
