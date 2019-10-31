---
title: ICorDebugThread::GetActiveFrame (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
ms.openlocfilehash: d623893bd77e46832b0bd823ed60c23e4eee29ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133541"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="86c08-102">ICorDebugThread::GetActiveFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="86c08-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="86c08-103">Obtiene un puntero de interfaz al marco activo (más reciente) en este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="86c08-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86c08-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86c08-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86c08-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86c08-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="86c08-106">enuncia Puntero a la dirección de un objeto de interfaz ICorDebugFrame que representa un marco.</span><span class="sxs-lookup"><span data-stu-id="86c08-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86c08-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="86c08-107">Remarks</span></span>  
 <span data-ttu-id="86c08-108">El parámetro `ppFrame` es NULL si no hay ningún fotograma activo actualmente.</span><span class="sxs-lookup"><span data-stu-id="86c08-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86c08-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86c08-109">Requirements</span></span>  
 <span data-ttu-id="86c08-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86c08-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86c08-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86c08-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86c08-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86c08-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86c08-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86c08-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
