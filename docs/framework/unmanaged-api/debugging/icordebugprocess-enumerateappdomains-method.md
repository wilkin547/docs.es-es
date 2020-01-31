---
title: ICorDebugProcess::EnumerateAppDomains (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnumerateAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type:
- apiref
ms.openlocfilehash: 35e3e37b1487b5dda9945402c6a3338384147f9a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792637"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="33252-102">ICorDebugProcess::EnumerateAppDomains (Método)</span><span class="sxs-lookup"><span data-stu-id="33252-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="33252-103">Enumera todos los dominios de aplicación de este proceso.</span><span class="sxs-lookup"><span data-stu-id="33252-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33252-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33252-104">Syntax</span></span>  
  
``` cpp 
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33252-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="33252-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="33252-106">enuncia Puntero a la dirección de un [ICorDebugAppDomainEnum (](icordebugappdomainenum-interface.md) que es un enumerador para los dominios de aplicación de este proceso.</span><span class="sxs-lookup"><span data-stu-id="33252-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33252-107">Notas</span><span class="sxs-lookup"><span data-stu-id="33252-107">Remarks</span></span>  
 <span data-ttu-id="33252-108">Este método se puede usar antes de la devolución de llamada [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="33252-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33252-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="33252-109">Requirements</span></span>  
 <span data-ttu-id="33252-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33252-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33252-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33252-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33252-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33252-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33252-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33252-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
