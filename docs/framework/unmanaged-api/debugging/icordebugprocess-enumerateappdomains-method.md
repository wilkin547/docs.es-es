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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02e051d311e447475bea724b0bd7420ee8b590f6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495733"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="a1218-102">ICorDebugProcess::EnumerateAppDomains (Método)</span><span class="sxs-lookup"><span data-stu-id="a1218-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="a1218-103">Enumera todos los dominios de aplicación en este proceso.</span><span class="sxs-lookup"><span data-stu-id="a1218-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1218-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1218-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1218-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1218-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="a1218-106">[out] Un puntero a la dirección de un [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) que es un enumerador para los dominios de aplicación en este proceso.</span><span class="sxs-lookup"><span data-stu-id="a1218-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1218-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a1218-107">Remarks</span></span>  
 <span data-ttu-id="a1218-108">Este método se puede usar antes del [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a1218-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1218-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1218-109">Requirements</span></span>  
 <span data-ttu-id="a1218-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1218-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1218-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1218-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1218-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1218-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1218-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1218-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
