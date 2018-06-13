---
title: ICorDebugModule3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugModule3
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3
helpviewer_keywords:
- ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fc4c0560c2aa0d66c1b40d78458a2d44284e232
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417920"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="bb8e4-102">ICorDebugModule3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb8e4-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="bb8e4-103">Crea un lector de símbolos para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="bb8e4-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb8e4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb8e4-104">Syntax</span></span>  
  
```  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bb8e4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="bb8e4-105">Methods</span></span>  
  
|<span data-ttu-id="bb8e4-106">Método</span><span class="sxs-lookup"><span data-stu-id="bb8e4-106">Method</span></span>|<span data-ttu-id="bb8e4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb8e4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb8e4-108">ICorDebugModule3::CreateReaderForInMemorySymbols (método)</span><span class="sxs-lookup"><span data-stu-id="bb8e4-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="bb8e4-109">Crea un lector de símbolos (normalmente [ISymUnmanagedReader (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="bb8e4-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb8e4-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb8e4-110">Remarks</span></span>  
 <span data-ttu-id="bb8e4-111">Esta interfaz extiende lógicamente las interfaces "ICorDebugModule" y "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="bb8e4-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb8e4-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="bb8e4-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb8e4-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb8e4-113">Requirements</span></span>  
 <span data-ttu-id="bb8e4-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb8e4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb8e4-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb8e4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb8e4-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb8e4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb8e4-117">**Versiones de .NET framework:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="bb8e4-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb8e4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb8e4-118">See Also</span></span>  
 [<span data-ttu-id="bb8e4-119">ICorDebugRemoteTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb8e4-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="bb8e4-120">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb8e4-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="bb8e4-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="bb8e4-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
