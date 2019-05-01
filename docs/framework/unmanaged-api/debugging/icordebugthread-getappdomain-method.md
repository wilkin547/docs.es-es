---
title: ICorDebugThread::GetAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetAppDomain
helpviewer_keywords:
- GetAppDomain method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetAppDomain method [.NET Framework debugging]
ms.assetid: 415b3d34-8b35-4b60-a318-140646cc83f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12a37ee8367006975b0f8ee4fa638ae3d72f9486
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987134"
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="e3ce2-102">ICorDebugThread::GetAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="e3ce2-102">ICorDebugThread::GetAppDomain Method</span></span>
<span data-ttu-id="e3ce2-103">Obtiene un puntero de interfaz al dominio de aplicación en el que se está ejecutando actualmente este ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="e3ce2-103">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3ce2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3ce2-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3ce2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e3ce2-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="e3ce2-106">[out] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se está ejecutando este subproceso.</span><span class="sxs-lookup"><span data-stu-id="e3ce2-106">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3ce2-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3ce2-107">Requirements</span></span>  
 <span data-ttu-id="e3ce2-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3ce2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3ce2-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3ce2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3ce2-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3ce2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3ce2-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3ce2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
