---
description: 'Más información acerca de: interfaz ICorDebugModule3'
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
ms.openlocfilehash: 5b47cffb267ab97de2cd225aca2998962ba66d99
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790768"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="92c3f-103">ICorDebugModule3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="92c3f-103">ICorDebugModule3 Interface</span></span>

<span data-ttu-id="92c3f-104">Crea un lector de símbolos para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="92c3f-104">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92c3f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92c3f-105">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="92c3f-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="92c3f-106">Methods</span></span>  
  
|<span data-ttu-id="92c3f-107">Método</span><span class="sxs-lookup"><span data-stu-id="92c3f-107">Method</span></span>|<span data-ttu-id="92c3f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="92c3f-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="92c3f-109">ICorDebugModule3::CreateReaderForInMemorySymbols (Método)</span><span class="sxs-lookup"><span data-stu-id="92c3f-109">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="92c3f-110">Crea un lector de símbolos (normalmente la [interfaz ISymUnmanagedReader](../diagnostics/isymunmanagedreader-interface.md)) para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="92c3f-110">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92c3f-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="92c3f-111">Remarks</span></span>  

 <span data-ttu-id="92c3f-112">Esta interfaz extiende lógicamente las interfaces "ICorDebugModule" y "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="92c3f-112">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="92c3f-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="92c3f-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92c3f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92c3f-114">Requirements</span></span>  

 <span data-ttu-id="92c3f-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92c3f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92c3f-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92c3f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92c3f-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92c3f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92c3f-118">**.NET Framework versiones:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="92c3f-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="92c3f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="92c3f-119">See also</span></span>

- [<span data-ttu-id="92c3f-120">ICorDebugRemoteTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="92c3f-120">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="92c3f-121">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="92c3f-121">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="92c3f-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="92c3f-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
