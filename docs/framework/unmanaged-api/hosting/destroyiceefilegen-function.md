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
ms.openlocfilehash: ab4560774edce49341c86dd9446e38701db7fa62
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769823"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="70037-102">DestroyICeeFileGen (Función)</span><span class="sxs-lookup"><span data-stu-id="70037-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="70037-103">Destruye un [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="70037-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="70037-104">Esta función está desusada en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="70037-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70037-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70037-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70037-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70037-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="70037-107">[in] La `ICeeFileGen` objeto que se va a destruir.</span><span class="sxs-lookup"><span data-stu-id="70037-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70037-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="70037-108">Return Value</span></span>  
 <span data-ttu-id="70037-109">Este método devuelve códigos de error COM estándar.</span><span class="sxs-lookup"><span data-stu-id="70037-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70037-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="70037-110">Remarks</span></span>  
 <span data-ttu-id="70037-111">`DestroyICeeFileGen` destruye el `ICeeFileGen` objeto creado por el [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="70037-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70037-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70037-112">Requirements</span></span>  
 <span data-ttu-id="70037-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70037-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70037-114">**Encabezado**: ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="70037-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="70037-115">**Biblioteca:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="70037-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="70037-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70037-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70037-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="70037-117">See also</span></span>

- [<span data-ttu-id="70037-118">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="70037-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
