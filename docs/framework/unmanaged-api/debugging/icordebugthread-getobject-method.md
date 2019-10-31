---
title: ICorDebugThread::GetObject (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetObject method [.NET Framework debugging]
ms.assetid: 1590febe-96c2-4046-97db-d81d81d67e01
topic_type:
- apiref
ms.openlocfilehash: 5cb95fb7cf70dbf7616e9bc59ebf44de090de883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133433"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="1b7a1-102">ICorDebugThread::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="1b7a1-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="1b7a1-103">Obtiene un puntero de interfaz al subproceso de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="1b7a1-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b7a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b7a1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b7a1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1b7a1-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="1b7a1-106">enuncia Puntero a la dirección de un objeto de interfaz ICorDebugValue que representa el subproceso de CLR.</span><span class="sxs-lookup"><span data-stu-id="1b7a1-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b7a1-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b7a1-107">Requirements</span></span>  
 <span data-ttu-id="1b7a1-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b7a1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b7a1-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b7a1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b7a1-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b7a1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b7a1-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b7a1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b7a1-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b7a1-112">See also</span></span>

- <xref:System.Threading.Thread>
