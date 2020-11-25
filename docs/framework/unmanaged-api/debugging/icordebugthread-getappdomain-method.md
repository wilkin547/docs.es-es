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
ms.openlocfilehash: 882176f381a7c5bc4a0297021b89a96948a1cea8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728074"
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="49251-102">ICorDebugThread::GetAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="49251-102">ICorDebugThread::GetAppDomain Method</span></span>

<span data-ttu-id="49251-103">Obtiene un puntero de interfaz al dominio de aplicación en el que se está ejecutando esta expresión ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="49251-103">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49251-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49251-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49251-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="49251-105">Parameters</span></span>  

 `ppAppDomain`  
 <span data-ttu-id="49251-106">enuncia Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se está ejecutando actualmente este subproceso.</span><span class="sxs-lookup"><span data-stu-id="49251-106">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49251-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49251-107">Requirements</span></span>  

 <span data-ttu-id="49251-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49251-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49251-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49251-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49251-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49251-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49251-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49251-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
