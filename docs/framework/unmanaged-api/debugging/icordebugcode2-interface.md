---
title: Interfaz ICorDebugCode2
ms.date: 03/30/2017
api_name:
- ICorDebugCode2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2
helpviewer_keywords:
- ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type:
- apiref
ms.openlocfilehash: 1e5b92d99d8ae52c88f1517f9c3d7db8e70598ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720807"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="4d305-102">Interfaz ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="4d305-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="4d305-103">Proporciona métodos que amplían las capacidades de "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="4d305-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4d305-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="4d305-104">Methods</span></span>  
  
|<span data-ttu-id="4d305-105">Método</span><span class="sxs-lookup"><span data-stu-id="4d305-105">Method</span></span>|<span data-ttu-id="4d305-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d305-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d305-107">Método GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="4d305-107">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="4d305-108">Obtiene los fragmentos de código de los que está compuesto este objeto de código.</span><span class="sxs-lookup"><span data-stu-id="4d305-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="4d305-109">Método GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="4d305-109">GetCompilerFlags Method</span></span>](icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="4d305-110">Obtiene las marcas que especifican las condiciones bajo las que este objeto de código se compiló Just-In-Time (JIT) o se generó usando el generador de imágenes nativas (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="4d305-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d305-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d305-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4d305-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="4d305-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d305-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d305-113">Requirements</span></span>  

 <span data-ttu-id="4d305-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d305-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d305-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d305-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d305-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d305-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d305-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d305-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d305-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d305-118">See also</span></span>

- [<span data-ttu-id="4d305-119">ICorDebugCode3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d305-119">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="4d305-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="4d305-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
