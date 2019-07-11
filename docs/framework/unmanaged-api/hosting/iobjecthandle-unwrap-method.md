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
ms.openlocfilehash: dc5bed553ac54eb708beae23f5c29cbedcb2b4e0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749067"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="b355f-102">IObjectHandle::Unwrap (Método)</span><span class="sxs-lookup"><span data-stu-id="b355f-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="b355f-103">Desencapsula un objeto de cálculo de referencias por valor desde el direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="b355f-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b355f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b355f-104">Syntax</span></span>  
  
```cpp  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b355f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b355f-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="b355f-106">[out] Un puntero al objeto que se debe desencapsular.</span><span class="sxs-lookup"><span data-stu-id="b355f-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b355f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b355f-107">Requirements</span></span>  
 <span data-ttu-id="b355f-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b355f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b355f-109">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b355f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b355f-110">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b355f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b355f-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b355f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
