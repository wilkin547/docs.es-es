---
title: "DestroyICeeFileGen (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type: COM
f1_keywords: DestroyICeeFileGen
helpviewer_keywords: DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6c3e326aa71adc1bc9abe350cfc0528c88905cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="9f839-102">DestroyICeeFileGen (Función)</span><span class="sxs-lookup"><span data-stu-id="9f839-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="9f839-103">Destruye una [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="9f839-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="9f839-104">Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f839-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f839-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f839-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f839-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9f839-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="9f839-107">[in] La `ICeeFileGen` objeto que se va a destruir.</span><span class="sxs-lookup"><span data-stu-id="9f839-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f839-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9f839-108">Return Value</span></span>  
 <span data-ttu-id="9f839-109">Este método devuelve los códigos de error COM estándar.</span><span class="sxs-lookup"><span data-stu-id="9f839-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f839-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9f839-110">Remarks</span></span>  
 <span data-ttu-id="9f839-111">`DestroyICeeFileGen`destruye el `ICeeFileGen` objeto creado por el [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="9f839-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f839-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f839-112">Requirements</span></span>  
 <span data-ttu-id="9f839-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f839-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f839-114">**Encabezado:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="9f839-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="9f839-115">**Biblioteca:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="9f839-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="9f839-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f839-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f839-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f839-117">See Also</span></span>  
 [<span data-ttu-id="9f839-118">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="9f839-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
