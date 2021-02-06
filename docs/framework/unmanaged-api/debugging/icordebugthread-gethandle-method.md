---
description: 'Más información acerca de: ICorDebugThread:: GetHandle (método)'
title: ICorDebugThread::GetHandle (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
ms.openlocfilehash: 378bb395e56f0fc287a480d67d2047e082d0796f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659106"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="6a79b-103">ICorDebugThread::GetHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="6a79b-103">ICorDebugThread::GetHandle Method</span></span>

<span data-ttu-id="6a79b-104">Obtiene el identificador actual para la parte activa de esta ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="6a79b-104">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a79b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a79b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a79b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6a79b-106">Parameters</span></span>  

 `phThreadHandle`  
 <span data-ttu-id="6a79b-107">enuncia Un puntero a un HTHREAD que es el identificador de la parte activa de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="6a79b-107">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a79b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6a79b-108">Remarks</span></span>  

 <span data-ttu-id="6a79b-109">El identificador puede cambiar a medida que se ejecuta el proceso y puede ser diferente para distintas partes del subproceso.</span><span class="sxs-lookup"><span data-stu-id="6a79b-109">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="6a79b-110">Este identificador es propiedad de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="6a79b-110">This handle is owned by the debugging API.</span></span> <span data-ttu-id="6a79b-111">El depurador debe duplicarlo antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="6a79b-111">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a79b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a79b-112">Requirements</span></span>  

 <span data-ttu-id="6a79b-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a79b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a79b-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a79b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a79b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a79b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a79b-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a79b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
