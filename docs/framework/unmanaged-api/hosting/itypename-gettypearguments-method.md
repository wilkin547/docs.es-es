---
description: 'Más información sobre: ITypeName:: Gettypearguments ((método)'
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
ms.openlocfilehash: b88ffcfb856905bf891ebeafa1e6dbeda2563aaf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753669"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="5a94f-103">ITypeName::GetTypeArguments (Método)</span><span class="sxs-lookup"><span data-stu-id="5a94f-103">ITypeName::GetTypeArguments Method</span></span>

<span data-ttu-id="5a94f-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="5a94f-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a94f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a94f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5a94f-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a94f-106">Requirements</span></span>  

 <span data-ttu-id="5a94f-107">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a94f-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a94f-108">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5a94f-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a94f-109">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a94f-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a94f-110">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a94f-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a94f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a94f-111">See also</span></span>

- [<span data-ttu-id="5a94f-112">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="5a94f-112">Hosting Interfaces</span></span>](hosting-interfaces.md)
