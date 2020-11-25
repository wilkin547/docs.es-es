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
ms.openlocfilehash: 2c13ead228296525b57245be8b3bdbcdf38ae173
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728009"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="bcd73-102">ICorDebugThread::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="bcd73-102">ICorDebugThread::GetObject Method</span></span>

<span data-ttu-id="bcd73-103">Obtiene un puntero de interfaz al subproceso de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="bcd73-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcd73-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bcd73-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcd73-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bcd73-105">Parameters</span></span>  

 `ppObject`  
 <span data-ttu-id="bcd73-106">enuncia Puntero a la dirección de un objeto de interfaz ICorDebugValue que representa el subproceso de CLR.</span><span class="sxs-lookup"><span data-stu-id="bcd73-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcd73-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bcd73-107">Requirements</span></span>  

 <span data-ttu-id="bcd73-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcd73-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcd73-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bcd73-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bcd73-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcd73-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcd73-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcd73-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcd73-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bcd73-112">See also</span></span>

- <xref:System.Threading.Thread>
