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
ms.openlocfilehash: 33acc4d9a0819c43d17c362fcbea2e7636521fd3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792933"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="7c153-102">ICorDebugModule3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c153-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="7c153-103">Crea un lector de símbolos para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="7c153-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c153-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c153-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7c153-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7c153-105">Methods</span></span>  
  
|<span data-ttu-id="7c153-106">Método</span><span class="sxs-lookup"><span data-stu-id="7c153-106">Method</span></span>|<span data-ttu-id="7c153-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c153-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7c153-108">ICorDebugModule3::CreateReaderForInMemorySymbols (método)</span><span class="sxs-lookup"><span data-stu-id="7c153-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="7c153-109">Crea un lector de símbolos (normalmente la [interfaz ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="7c153-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c153-110">Notas</span><span class="sxs-lookup"><span data-stu-id="7c153-110">Remarks</span></span>  
 <span data-ttu-id="7c153-111">Esta interfaz extiende lógicamente las interfaces "ICorDebugModule" y "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="7c153-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c153-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="7c153-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c153-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="7c153-113">Requirements</span></span>  
 <span data-ttu-id="7c153-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c153-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c153-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c153-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c153-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c153-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c153-117">**.NET Framework versiones:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="7c153-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7c153-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c153-118">See also</span></span>

- [<span data-ttu-id="7c153-119">ICorDebugRemoteTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c153-119">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="7c153-120">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c153-120">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="7c153-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7c153-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
