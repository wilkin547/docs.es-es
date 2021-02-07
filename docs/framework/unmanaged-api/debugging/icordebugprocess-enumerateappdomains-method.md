---
description: 'Más información acerca de: ICorDebugProcess:: Enumerateappdomains ((método)'
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
ms.openlocfilehash: d212fafe7ae1355ba69e07b88c3b96119371fe43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691528"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="3c99f-103">ICorDebugProcess::EnumerateAppDomains (Método)</span><span class="sxs-lookup"><span data-stu-id="3c99f-103">ICorDebugProcess::EnumerateAppDomains Method</span></span>

<span data-ttu-id="3c99f-104">Enumera todos los dominios de aplicación de este proceso.</span><span class="sxs-lookup"><span data-stu-id="3c99f-104">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c99f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c99f-105">Syntax</span></span>  
  
``` cpp
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c99f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c99f-106">Parameters</span></span>  

 `ppAppDomains`  
 <span data-ttu-id="3c99f-107">enuncia Puntero a la dirección de un [ICorDebugAppDomainEnum (](icordebugappdomainenum-interface.md) que es un enumerador para los dominios de aplicación de este proceso.</span><span class="sxs-lookup"><span data-stu-id="3c99f-107">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c99f-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3c99f-108">Remarks</span></span>  

 <span data-ttu-id="3c99f-109">Este método se puede usar antes de la devolución de llamada [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3c99f-109">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c99f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c99f-110">Requirements</span></span>  

 <span data-ttu-id="3c99f-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c99f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c99f-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c99f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c99f-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c99f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c99f-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c99f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
