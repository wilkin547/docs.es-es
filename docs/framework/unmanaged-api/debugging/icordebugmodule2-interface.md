---
description: 'Más información acerca de: interfaz ICorDebugModule2'
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
ms.openlocfilehash: 28de1f0d3411218ac92991d4fceda0612c8199bf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659938"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="a44b1-103">Interfaz ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="a44b1-103">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="a44b1-104">Actúa como una extensión lógica de la interfaz ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="a44b1-104">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a44b1-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a44b1-105">Methods</span></span>  
  
|<span data-ttu-id="a44b1-106">Método</span><span class="sxs-lookup"><span data-stu-id="a44b1-106">Method</span></span>|<span data-ttu-id="a44b1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a44b1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a44b1-108">Método ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="a44b1-108">ApplyChanges Method</span></span>](icordebugmodule2-applychanges-method.md)|<span data-ttu-id="a44b1-109">Aplica los cambios en los metadatos y los cambios en el código del lenguaje intermedio de Microsoft (MSIL) al proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="a44b1-109">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="a44b1-110">Método GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="a44b1-110">GetJITCompilerFlags Method</span></span>](icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="a44b1-111">Obtiene las marcas que controlan la compilación Just-in-Time (JIT) para este `ICorDebugModule2` .</span><span class="sxs-lookup"><span data-stu-id="a44b1-111">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="a44b1-112">Método ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="a44b1-112">ResolveAssembly Method</span></span>](icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="a44b1-113">Resuelve el ensamblado al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="a44b1-113">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="a44b1-114">Método SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="a44b1-114">SetJITCompilerFlags Method</span></span>](icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="a44b1-115">Establece las marcas que controlan la compilación JIT para este `ICorDebugModule2` .</span><span class="sxs-lookup"><span data-stu-id="a44b1-115">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="a44b1-116">SetJMCStatus (Método)</span><span class="sxs-lookup"><span data-stu-id="a44b1-116">SetJMCStatus Method</span></span>](icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="a44b1-117">Establece el Estado Solo mi código (JMC) de todos los métodos de todas las clases de este en `ICorDebugModule2` el valor especificado, excepto los de la `pTokens` matriz, que establece en el valor opuesto.</span><span class="sxs-lookup"><span data-stu-id="a44b1-117">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a44b1-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a44b1-118">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a44b1-119">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a44b1-119">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a44b1-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a44b1-120">Requirements</span></span>  

 <span data-ttu-id="a44b1-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a44b1-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a44b1-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a44b1-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a44b1-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a44b1-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a44b1-124">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a44b1-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a44b1-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a44b1-125">See also</span></span>

- [<span data-ttu-id="a44b1-126">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a44b1-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
