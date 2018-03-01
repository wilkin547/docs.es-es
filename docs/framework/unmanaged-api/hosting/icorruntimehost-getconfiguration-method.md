---
title: "ICorRuntimeHost::GetConfiguration (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 446142d8bd61d384c3b8a58d5469e27a7a512c60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="56cec-102">ICorRuntimeHost::GetConfiguration (Método)</span><span class="sxs-lookup"><span data-stu-id="56cec-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="56cec-103">Obtiene un objeto que permite al host especificar la configuración de devolución de llamada de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="56cec-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56cec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56cec-104">Syntax</span></span>  
  
```  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56cec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="56cec-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="56cec-106">[out] Un puntero a la dirección de un [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) objeto que puede usar para configurar el CLR.</span><span class="sxs-lookup"><span data-stu-id="56cec-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56cec-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="56cec-107">Remarks</span></span>  
 <span data-ttu-id="56cec-108">El CLR debe configurarse antes de su inicialización; en caso contrario, el `GetConfiguration` método devuelve un HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="56cec-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56cec-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56cec-109">Requirements</span></span>  
 <span data-ttu-id="56cec-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56cec-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56cec-111">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="56cec-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="56cec-112">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="56cec-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56cec-113">**Versiones de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="56cec-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56cec-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="56cec-114">See Also</span></span>  
 [<span data-ttu-id="56cec-115">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="56cec-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
