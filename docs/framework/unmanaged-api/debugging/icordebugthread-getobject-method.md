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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fa90aff73d94baf2cbf7d01f41710cb2aa10213
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994011"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="4b3fc-102">ICorDebugThread::GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="4b3fc-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="4b3fc-103">Obtiene un puntero de interfaz para el subproceso de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4b3fc-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b3fc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b3fc-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b3fc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4b3fc-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="4b3fc-106">[out] Un puntero a la dirección de un objeto de interfaz ICorDebugValue que representa el subproceso de CLR.</span><span class="sxs-lookup"><span data-stu-id="4b3fc-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b3fc-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b3fc-107">Requirements</span></span>  
 <span data-ttu-id="4b3fc-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b3fc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b3fc-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b3fc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b3fc-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b3fc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b3fc-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b3fc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b3fc-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b3fc-112">See also</span></span>

- <xref:System.Threading.Thread>
