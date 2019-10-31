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
ms.openlocfilehash: 4eb878b61b72378bc6870af7f2cd09f0b6943b13
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136501"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="d8d0c-102">DestroyICeeFileGen (Función)</span><span class="sxs-lookup"><span data-stu-id="d8d0c-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="d8d0c-103">Destruye un objeto [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="d8d0c-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="d8d0c-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d8d0c-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8d0c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8d0c-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8d0c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8d0c-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="d8d0c-107">de Objeto `ICeeFileGen` que se va a destruir.</span><span class="sxs-lookup"><span data-stu-id="d8d0c-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8d0c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d8d0c-108">Return Value</span></span>  
 <span data-ttu-id="d8d0c-109">Este método devuelve los códigos de error COM estándar.</span><span class="sxs-lookup"><span data-stu-id="d8d0c-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8d0c-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8d0c-110">Remarks</span></span>  
 <span data-ttu-id="d8d0c-111">`DestroyICeeFileGen` destruye el `ICeeFileGen` objeto creado por la función [CreateICeeFileGen (](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) .</span><span class="sxs-lookup"><span data-stu-id="d8d0c-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8d0c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8d0c-112">Requirements</span></span>  
 <span data-ttu-id="d8d0c-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8d0c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8d0c-114">**Encabezado:** ICeeFileGen. h</span><span class="sxs-lookup"><span data-stu-id="d8d0c-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="d8d0c-115">**Biblioteca:** MSCorPE. dll</span><span class="sxs-lookup"><span data-stu-id="d8d0c-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="d8d0c-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8d0c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d0c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8d0c-117">See also</span></span>

- [<span data-ttu-id="d8d0c-118">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="d8d0c-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
