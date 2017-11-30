---
title: "ICorRuntimeHost::SwitchInLogicalThreadState (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.SwitchInLogicalThreadState
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b17927498c5f9000d6c7c0e32d46f6f87a9c78af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="8024f-102">ICorRuntimeHost::SwitchInLogicalThreadState (Método)</span><span class="sxs-lookup"><span data-stu-id="8024f-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="8024f-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="8024f-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8024f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8024f-104">Syntax</span></span>  
  
```  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8024f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8024f-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="8024f-106">[in] Cookie que indica la fibra para usar.</span><span class="sxs-lookup"><span data-stu-id="8024f-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8024f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8024f-107">Requirements</span></span>  
 <span data-ttu-id="8024f-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8024f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8024f-109">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8024f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8024f-110">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8024f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8024f-111">**Versión de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="8024f-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8024f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8024f-112">See Also</span></span>  
 [<span data-ttu-id="8024f-113">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8024f-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
