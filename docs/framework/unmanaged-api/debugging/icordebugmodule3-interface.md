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
ms.openlocfilehash: 58bad617eb91b7e529ff3d95edd06a5c73feee64
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46472040"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="eb996-102">ICorDebugModule3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb996-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="eb996-103">Crea un lector de símbolos para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="eb996-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb996-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb996-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="eb996-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="eb996-105">Methods</span></span>  
  
|<span data-ttu-id="eb996-106">Método</span><span class="sxs-lookup"><span data-stu-id="eb996-106">Method</span></span>|<span data-ttu-id="eb996-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb996-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb996-108">ICorDebugModule3::CreateReaderForInMemorySymbols (método)</span><span class="sxs-lookup"><span data-stu-id="eb996-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="eb996-109">Crea un lector de símbolos (normalmente [interfaz ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="eb996-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb996-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eb996-110">Remarks</span></span>  
 <span data-ttu-id="eb996-111">Esta interfaz extiende lógicamente las interfaces "ICorDebugModule" y "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="eb996-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb996-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="eb996-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb996-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb996-113">Requirements</span></span>  
 <span data-ttu-id="eb996-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb996-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb996-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb996-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb996-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb996-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb996-117">**Versiones de .NET framework:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="eb996-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eb996-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb996-118">See Also</span></span>  
 [<span data-ttu-id="eb996-119">ICorDebugRemoteTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb996-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="eb996-120">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb996-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="eb996-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="eb996-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
