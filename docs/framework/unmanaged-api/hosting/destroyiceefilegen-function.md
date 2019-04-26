---
title: DestroyICeeFileGen (Función)
ms.date: 03/30/2017
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37ff40e1c009b8e1e0509a4a3333d5a2a70bbfd2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906365"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="10890-102">DestroyICeeFileGen (Función)</span><span class="sxs-lookup"><span data-stu-id="10890-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="10890-103">Destruye un [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="10890-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="10890-104">Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10890-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10890-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10890-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10890-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="10890-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="10890-107">[in] La `ICeeFileGen` objeto que se va a destruir.</span><span class="sxs-lookup"><span data-stu-id="10890-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10890-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="10890-108">Return Value</span></span>  
 <span data-ttu-id="10890-109">Este método devuelve códigos de error COM estándar.</span><span class="sxs-lookup"><span data-stu-id="10890-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10890-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="10890-110">Remarks</span></span>  
 <span data-ttu-id="10890-111">`DestroyICeeFileGen` destruye el `ICeeFileGen` objeto creado por el [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="10890-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10890-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10890-112">Requirements</span></span>  
 <span data-ttu-id="10890-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10890-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10890-114">**Encabezado**: ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="10890-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="10890-115">**Biblioteca:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="10890-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="10890-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10890-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10890-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="10890-117">See also</span></span>

- [<span data-ttu-id="10890-118">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="10890-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
