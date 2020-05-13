---
title: ICorDebugThread4::GetBlockingObjects (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
ms.openlocfilehash: 366b5124cc66a4e9a1c3bd4e77f604f15ba8d8a8
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379671"
---
# <a name="icordebugthread4getblockingobjects-method"></a><span data-ttu-id="72f69-102">ICorDebugThread4::GetBlockingObjects (Método)</span><span class="sxs-lookup"><span data-stu-id="72f69-102">ICorDebugThread4::GetBlockingObjects Method</span></span>
<span data-ttu-id="72f69-103">Proporciona una enumeración ordenada de las estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) que proporcionan información de bloqueo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="72f69-103">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72f69-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72f69-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a><span data-ttu-id="72f69-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72f69-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="72f69-106">enuncia Puntero a una enumeración ordenada de estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="72f69-106">[out] A pointer to an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72f69-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="72f69-107">Remarks</span></span>  
 <span data-ttu-id="72f69-108">El primer elemento de la enumeración devuelta corresponde a la primera estructura que está bloqueando el subproceso.</span><span class="sxs-lookup"><span data-stu-id="72f69-108">The first element in the returned enumeration corresponds to the first structure that is blocking the thread.</span></span> <span data-ttu-id="72f69-109">El segundo elemento corresponde a un elemento de bloqueo que se encuentra mientras se ejecuta una llamada a procedimiento asincrónico (APC) cuando se bloquea en el primero, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="72f69-109">The second element corresponds to a blocking item that is encountered while running an asynchronous procedure call (APC) when blocked on the first, and so on.</span></span>  
  
 <span data-ttu-id="72f69-110">La enumeración solo es válida para la duración del estado sincronizado actual.</span><span class="sxs-lookup"><span data-stu-id="72f69-110">The enumeration is valid only for the duration of the current synchronized state.</span></span>  
  
 <span data-ttu-id="72f69-111">Se debe llamar a este método mientras el código depurado esté en un estado sincronizado.</span><span class="sxs-lookup"><span data-stu-id="72f69-111">This method must be called while the debuggee is in a synchronized state.</span></span>  
  
 <span data-ttu-id="72f69-112">Si `ppBlockingObjectEnum` no es un puntero válido, el resultado es indefinido.</span><span class="sxs-lookup"><span data-stu-id="72f69-112">If `ppBlockingObjectEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="72f69-113">Si un subproceso está bloqueado y no se puede determinar el error, el método devuelve un valor HRESULT que indica un error. de lo contrario, Devuelve S_OK.</span><span class="sxs-lookup"><span data-stu-id="72f69-113">If a thread is blocked and the error cannot be determined, the method returns an HRESULT that indicates failure; otherwise, it returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72f69-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72f69-114">Requirements</span></span>  
 <span data-ttu-id="72f69-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72f69-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72f69-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72f69-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72f69-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72f69-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72f69-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72f69-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72f69-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="72f69-119">See also</span></span>

- [<span data-ttu-id="72f69-120">ICorDebugThread4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="72f69-120">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="72f69-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="72f69-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="72f69-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="72f69-122">Debugging</span></span>](index.md)
