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
ms.openlocfilehash: 543a1a3c79b6cf3eb799da5844f35286dfa91940
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709562"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="86043-102">ICorDebugModule3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86043-102">ICorDebugModule3 Interface</span></span>

<span data-ttu-id="86043-103">Crea un lector de símbolos para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="86043-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86043-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86043-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="86043-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="86043-105">Methods</span></span>  
  
|<span data-ttu-id="86043-106">Método</span><span class="sxs-lookup"><span data-stu-id="86043-106">Method</span></span>|<span data-ttu-id="86043-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="86043-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="86043-108">ICorDebugModule3::CreateReaderForInMemorySymbols (Método)</span><span class="sxs-lookup"><span data-stu-id="86043-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="86043-109">Crea un lector de símbolos (normalmente la [interfaz ISymUnmanagedReader](../diagnostics/isymunmanagedreader-interface.md)) para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="86043-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86043-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="86043-110">Remarks</span></span>  

 <span data-ttu-id="86043-111">Esta interfaz extiende lógicamente las interfaces "ICorDebugModule" y "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="86043-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86043-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="86043-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86043-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86043-113">Requirements</span></span>  

 <span data-ttu-id="86043-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86043-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86043-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86043-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86043-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86043-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86043-117">**.NET Framework versiones:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="86043-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="86043-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86043-118">See also</span></span>

- [<span data-ttu-id="86043-119">ICorDebugRemoteTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86043-119">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="86043-120">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86043-120">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="86043-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="86043-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
