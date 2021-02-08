---
description: 'Más información sobre: ICorDebugThread4:: HadUnhandledException ((método)'
title: ICorDebugThread4::HadUnhandledException (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
ms.openlocfilehash: cd0ccdbdd68c37b5fbdbd705da7136e5d36baa60
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800934"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="7b305-103">ICorDebugThread4::HadUnhandledException (Método)</span><span class="sxs-lookup"><span data-stu-id="7b305-103">ICorDebugThread4::HadUnhandledException Method</span></span>

<span data-ttu-id="7b305-104">Indica si el subproceso ha tenido alguna vez una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="7b305-104">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b305-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b305-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b305-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b305-106">Parameters</span></span>  

 `ppBlockingObjectEnum`  
 <span data-ttu-id="7b305-107">enuncia Puntero a la dirección de una enumeración ordenada de estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="7b305-107">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b305-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7b305-108">Return Value</span></span>  

 <span data-ttu-id="7b305-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="7b305-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7b305-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7b305-110">HRESULT</span></span>|<span data-ttu-id="7b305-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b305-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7b305-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7b305-112">S_OK</span></span>|<span data-ttu-id="7b305-113">El subproceso ha tenido una excepción no controlada desde su creación.</span><span class="sxs-lookup"><span data-stu-id="7b305-113">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="7b305-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7b305-114">S_FALSE</span></span>|<span data-ttu-id="7b305-115">El subproceso nunca ha tenido una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="7b305-115">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b305-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7b305-116">Remarks</span></span>  

 <span data-ttu-id="7b305-117">Este método indica si el subproceso ha tenido alguna vez una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="7b305-117">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="7b305-118">En el momento en que se desencadena la devolución de llamada de excepción no controlada o se inicia la Asociación JIT nativa, se garantiza que este método devuelve S_OK.</span><span class="sxs-lookup"><span data-stu-id="7b305-118">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="7b305-119">No hay ninguna garantía de que el método [ICorDebugThread. GetCurrentException (](icordebugthread-getcurrentexception-method.md) devuelva la excepción no controlada. sin embargo, si el proceso aún no se ha continuado después de obtener la devolución de llamada de excepción no controlada o después de la Asociación JIT nativa.</span><span class="sxs-lookup"><span data-stu-id="7b305-119">There is no guarantee that the [ICorDebugThread.GetCurrentException](icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="7b305-120">Además, es posible (aunque improbable) tener más de un subproceso con una excepción no controlada en el momento en que se desencadena la Asociación JIT nativa.</span><span class="sxs-lookup"><span data-stu-id="7b305-120">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="7b305-121">En tal caso, no hay ninguna manera de determinar qué excepción desencadenó la Asociación JIT.</span><span class="sxs-lookup"><span data-stu-id="7b305-121">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b305-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b305-122">Requirements</span></span>  

 <span data-ttu-id="7b305-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b305-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b305-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b305-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b305-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b305-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b305-126">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b305-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b305-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b305-127">See also</span></span>

- [<span data-ttu-id="7b305-128">ICorDebugThread4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b305-128">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="7b305-129">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="7b305-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7b305-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="7b305-130">Debugging</span></span>](index.md)
