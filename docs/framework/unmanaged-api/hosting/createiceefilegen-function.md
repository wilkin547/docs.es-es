---
title: CreateICeeFileGen (Función)
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: de27851b4afc3eccad46531848c68723bff346d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136832"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="03a5d-102">CreateICeeFileGen (Función)</span><span class="sxs-lookup"><span data-stu-id="03a5d-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="03a5d-103">Crea un objeto [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="03a5d-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="03a5d-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="03a5d-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03a5d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03a5d-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03a5d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03a5d-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="03a5d-107">enuncia Puntero a la dirección de un nuevo objeto de `ICeeFileGen`.</span><span class="sxs-lookup"><span data-stu-id="03a5d-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03a5d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="03a5d-108">Return Value</span></span>  
 <span data-ttu-id="03a5d-109">Este método devuelve los códigos de error COM estándar.</span><span class="sxs-lookup"><span data-stu-id="03a5d-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03a5d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="03a5d-110">Remarks</span></span>  
 <span data-ttu-id="03a5d-111">El objeto `ICeeFileGen` se usa para crear archivos ejecutables portables (PE) de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="03a5d-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="03a5d-112">Llame a la función [DestroyICeeFileGen (](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) para destruir el objeto `ICeeFileGen` cuando termine.</span><span class="sxs-lookup"><span data-stu-id="03a5d-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03a5d-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03a5d-113">Requirements</span></span>  
 <span data-ttu-id="03a5d-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03a5d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03a5d-115">**Encabezado:** ICeeFileGen. h</span><span class="sxs-lookup"><span data-stu-id="03a5d-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="03a5d-116">**Biblioteca:** MSCorPE. dll</span><span class="sxs-lookup"><span data-stu-id="03a5d-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="03a5d-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03a5d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03a5d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="03a5d-118">See also</span></span>

- [<span data-ttu-id="03a5d-119">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="03a5d-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
