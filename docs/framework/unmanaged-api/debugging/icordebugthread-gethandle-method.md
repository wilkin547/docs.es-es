---
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
ms.openlocfilehash: 16aafa439fc81c3606f98ca2ba860316ec46e0db
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379739"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="64fa2-102">ICorDebugThread::GetHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="64fa2-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="64fa2-103">Obtiene el identificador actual para la parte activa de esta ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="64fa2-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64fa2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64fa2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64fa2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="64fa2-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="64fa2-106">enuncia Un puntero a un HTHREAD que es el identificador de la parte activa de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="64fa2-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64fa2-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="64fa2-107">Remarks</span></span>  
 <span data-ttu-id="64fa2-108">El identificador puede cambiar a medida que se ejecuta el proceso y puede ser diferente para distintas partes del subproceso.</span><span class="sxs-lookup"><span data-stu-id="64fa2-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="64fa2-109">Este identificador es propiedad de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="64fa2-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="64fa2-110">El depurador debe duplicarlo antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="64fa2-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64fa2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64fa2-111">Requirements</span></span>  
 <span data-ttu-id="64fa2-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64fa2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64fa2-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64fa2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64fa2-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64fa2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64fa2-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64fa2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
