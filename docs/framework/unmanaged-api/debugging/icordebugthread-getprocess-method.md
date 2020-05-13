---
title: ICorDebugThread::GetProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
ms.openlocfilehash: 76dfc10b9d9069f6d53cd292f241ae3080c6443a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379809"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="e7e99-102">ICorDebugThread::GetProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="e7e99-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="e7e99-103">Obtiene un puntero de interfaz al proceso del que esta expresión forma una parte.</span><span class="sxs-lookup"><span data-stu-id="e7e99-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7e99-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7e99-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7e99-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e7e99-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="e7e99-106">enuncia Puntero a la dirección de un objeto de interfaz ICorDebugProcess que representa el proceso.</span><span class="sxs-lookup"><span data-stu-id="e7e99-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7e99-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7e99-107">Requirements</span></span>  
 <span data-ttu-id="e7e99-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7e99-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7e99-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7e99-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7e99-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7e99-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7e99-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7e99-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
