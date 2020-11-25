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
ms.openlocfilehash: 2b8e6048dd6b8df71ac3dddcc4397f6d512127c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695886"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="c0456-102">Interfaz ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="c0456-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="c0456-103">Actúa como una extensión lógica de la interfaz ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="c0456-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c0456-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c0456-104">Methods</span></span>  
  
|<span data-ttu-id="c0456-105">Método</span><span class="sxs-lookup"><span data-stu-id="c0456-105">Method</span></span>|<span data-ttu-id="c0456-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0456-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c0456-107">Método ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="c0456-107">ApplyChanges Method</span></span>](icordebugmodule2-applychanges-method.md)|<span data-ttu-id="c0456-108">Aplica los cambios en los metadatos y los cambios en el código del lenguaje intermedio de Microsoft (MSIL) al proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="c0456-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="c0456-109">Método GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="c0456-109">GetJITCompilerFlags Method</span></span>](icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="c0456-110">Obtiene las marcas que controlan la compilación Just-in-Time (JIT) para este `ICorDebugModule2` .</span><span class="sxs-lookup"><span data-stu-id="c0456-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="c0456-111">Método ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="c0456-111">ResolveAssembly Method</span></span>](icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="c0456-112">Resuelve el ensamblado al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="c0456-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="c0456-113">Método SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="c0456-113">SetJITCompilerFlags Method</span></span>](icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="c0456-114">Establece las marcas que controlan la compilación JIT para este `ICorDebugModule2` .</span><span class="sxs-lookup"><span data-stu-id="c0456-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="c0456-115">SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="c0456-115">SetJMCStatus Method</span></span>](icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="c0456-116">Establece el Estado Solo mi código (JMC) de todos los métodos de todas las clases de este en `ICorDebugModule2` el valor especificado, excepto los de la `pTokens` matriz, que establece en el valor opuesto.</span><span class="sxs-lookup"><span data-stu-id="c0456-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0456-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0456-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c0456-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c0456-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0456-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0456-119">Requirements</span></span>  

 <span data-ttu-id="c0456-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0456-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0456-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0456-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0456-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0456-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0456-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0456-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0456-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0456-124">See also</span></span>

- [<span data-ttu-id="c0456-125">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c0456-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
