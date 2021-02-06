---
description: 'Más información acerca de: ICorDebugThread:: Getappdomain ((método)'
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
ms.openlocfilehash: 416ab80fa08786fb5e95776b164723317fa59ca6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659210"
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="ce904-103">ICorDebugThread::GetAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="ce904-103">ICorDebugThread::GetAppDomain Method</span></span>

<span data-ttu-id="ce904-104">Obtiene un puntero de interfaz al dominio de aplicación en el que se está ejecutando esta expresión ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="ce904-104">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce904-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce904-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce904-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce904-106">Parameters</span></span>  

 `ppAppDomain`  
 <span data-ttu-id="ce904-107">enuncia Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se está ejecutando actualmente este subproceso.</span><span class="sxs-lookup"><span data-stu-id="ce904-107">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce904-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce904-108">Requirements</span></span>  

 <span data-ttu-id="ce904-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce904-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce904-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce904-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce904-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce904-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce904-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce904-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
