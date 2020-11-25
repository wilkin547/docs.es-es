---
title: ITypeName::GetTypeArguments (Método)
ms.date: 03/30/2017
api_name:
- ITypeName.GetTypeArguments
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArguments
helpviewer_keywords:
- ITypeName::GetTypeArguments method [.NET Framework hosting]
- GetTypeArguments method [.NET Framework hosting]
ms.assetid: 638d77df-ff9c-40d9-88ee-930f5f87ada1
topic_type:
- apiref
ms.openlocfilehash: bcc1cb2755c4c0a2beb0829ce58b921f073f63d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727788"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="53a8b-102">ITypeName::GetTypeArguments (Método)</span><span class="sxs-lookup"><span data-stu-id="53a8b-102">ITypeName::GetTypeArguments Method</span></span>

<span data-ttu-id="53a8b-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="53a8b-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53a8b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53a8b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="53a8b-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53a8b-105">Requirements</span></span>  

 <span data-ttu-id="53a8b-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53a8b-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53a8b-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="53a8b-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53a8b-108">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="53a8b-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53a8b-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53a8b-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53a8b-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53a8b-110">See also</span></span>

- [<span data-ttu-id="53a8b-111">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="53a8b-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
