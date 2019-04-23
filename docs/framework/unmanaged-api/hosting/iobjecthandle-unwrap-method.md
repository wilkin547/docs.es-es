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
ms.openlocfilehash: 4c18607d5373b415228846350a3dd0637ade1b45
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150805"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="057d4-102">IObjectHandle::Unwrap (Método)</span><span class="sxs-lookup"><span data-stu-id="057d4-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="057d4-103">Desencapsula un objeto de cálculo de referencias por valor desde el direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="057d4-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="057d4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="057d4-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="057d4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="057d4-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="057d4-106">[out] Un puntero al objeto que se debe desencapsular.</span><span class="sxs-lookup"><span data-stu-id="057d4-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="057d4-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="057d4-107">Requirements</span></span>  
 <span data-ttu-id="057d4-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="057d4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="057d4-109">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="057d4-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="057d4-110">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="057d4-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="057d4-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="057d4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
