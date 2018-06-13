---
title: ITypeName::GetNames (Método)
ms.date: 03/30/2017
api_name:
- ITypeName.GetNames
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetNames
helpviewer_keywords:
- ITypeName::GetNames method [.NET Framework hosting]
- GetNames method [.NET Framework hosting]
ms.assetid: e2a3637b-d1e9-4d93-9e9b-0555fbff793d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d718564f4ed106956aadd2f54212f28e8cfc3de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440702"
---
# <a name="itypenamegetnames-method"></a><span data-ttu-id="d48c2-102">ITypeName::GetNames (Método)</span><span class="sxs-lookup"><span data-stu-id="d48c2-102">ITypeName::GetNames Method</span></span>
<span data-ttu-id="d48c2-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="d48c2-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d48c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d48c2-104">Syntax</span></span>  
  
```  
HRESULT GetNames (  
    [in] DWORD           count,  
    [out] BSTR*          rgbszNames,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="d48c2-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d48c2-105">Requirements</span></span>  
 <span data-ttu-id="d48c2-106">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d48c2-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d48c2-107">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d48c2-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d48c2-108">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d48c2-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d48c2-109">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d48c2-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d48c2-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d48c2-110">See Also</span></span>  
 [<span data-ttu-id="d48c2-111">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="d48c2-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
