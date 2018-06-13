---
title: IObjectHandle::Unwrap (Método)
ms.date: 03/30/2017
api_name:
- IObjectHandle.Unwrap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d9a8f9aa910054a4541e4ff8c1f7cad63077ba8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439955"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="e4799-102">IObjectHandle::Unwrap (Método)</span><span class="sxs-lookup"><span data-stu-id="e4799-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="e4799-103">Desencapsula un objeto de cálculo de referencias por valor de direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="e4799-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4799-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4799-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4799-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e4799-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="e4799-106">[out] Un puntero al objeto desempaquetarse.</span><span class="sxs-lookup"><span data-stu-id="e4799-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4799-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4799-107">Requirements</span></span>  
 <span data-ttu-id="e4799-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4799-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4799-109">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e4799-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e4799-110">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e4799-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4799-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4799-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4799-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4799-112">See Also</span></span>  
 
