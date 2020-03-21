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
ms.openlocfilehash: 4489238df05edef384b4073ee738a184ff8809ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178671"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="a856b-102">ICorDebugProcess::EnumerateAppDomains (Método)</span><span class="sxs-lookup"><span data-stu-id="a856b-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="a856b-103">Enumera todos los dominios de aplicación en este proceso.</span><span class="sxs-lookup"><span data-stu-id="a856b-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a856b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a856b-104">Syntax</span></span>  
  
``` cpp
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a856b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a856b-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="a856b-106">[fuera] Puntero a la dirección de un [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) que es un enumerador para los dominios de aplicación en este proceso.</span><span class="sxs-lookup"><span data-stu-id="a856b-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a856b-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a856b-107">Remarks</span></span>  
 <span data-ttu-id="a856b-108">Este método se puede usar antes de la [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a856b-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a856b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a856b-109">Requirements</span></span>  
 <span data-ttu-id="a856b-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a856b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a856b-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a856b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a856b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a856b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a856b-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a856b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
