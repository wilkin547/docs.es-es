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
ms.openlocfilehash: 37041764ad37221ea80cefa12adfb214287d8248
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764005"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="3917a-102">ICorDebugModule3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3917a-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="3917a-103">Crea un lector de símbolos para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="3917a-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3917a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3917a-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="3917a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3917a-105">Methods</span></span>  
  
|<span data-ttu-id="3917a-106">Método</span><span class="sxs-lookup"><span data-stu-id="3917a-106">Method</span></span>|<span data-ttu-id="3917a-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3917a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3917a-108">ICorDebugModule3::CreateReaderForInMemorySymbols (método)</span><span class="sxs-lookup"><span data-stu-id="3917a-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="3917a-109">Crea un lector de símbolos (normalmente [interfaz ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="3917a-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3917a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3917a-110">Remarks</span></span>  
 <span data-ttu-id="3917a-111">Esta interfaz extiende lógicamente las interfaces "ICorDebugModule" y "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="3917a-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3917a-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3917a-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3917a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3917a-113">Requirements</span></span>  
 <span data-ttu-id="3917a-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3917a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3917a-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3917a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3917a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3917a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3917a-117">**Versiones de .NET framework:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="3917a-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3917a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3917a-118">See also</span></span>

- [<span data-ttu-id="3917a-119">ICorDebugRemoteTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3917a-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="3917a-120">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3917a-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="3917a-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3917a-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
