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
ms.openlocfilehash: da473ed176ab6c69ed974d5f28b22fc8eb30c6af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762520"
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="0def6-102">ICorDebugThread::GetAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="0def6-102">ICorDebugThread::GetAppDomain Method</span></span>
<span data-ttu-id="0def6-103">Obtiene un puntero de interfaz al dominio de aplicación en el que se está ejecutando actualmente este ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="0def6-103">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0def6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0def6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0def6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0def6-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="0def6-106">[out] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se está ejecutando este subproceso.</span><span class="sxs-lookup"><span data-stu-id="0def6-106">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0def6-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0def6-107">Requirements</span></span>  
 <span data-ttu-id="0def6-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0def6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0def6-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0def6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0def6-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0def6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0def6-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0def6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
