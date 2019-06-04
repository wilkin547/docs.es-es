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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57163ccfcc6dff343a8bbc7d63564ae6b57b5ff6
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490496"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="29125-102">CreateICeeFileGen (Función)</span><span class="sxs-lookup"><span data-stu-id="29125-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="29125-103">Crea un [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="29125-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="29125-104">Esta función está desusada en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="29125-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29125-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29125-105">Syntax</span></span>  
  
```  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29125-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="29125-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="29125-107">[out] Un puntero a la dirección de un nuevo `ICeeFileGen` objeto.</span><span class="sxs-lookup"><span data-stu-id="29125-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="29125-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="29125-108">Return Value</span></span>  
 <span data-ttu-id="29125-109">Este método devuelve códigos de error COM estándar.</span><span class="sxs-lookup"><span data-stu-id="29125-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29125-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="29125-110">Remarks</span></span>  
 <span data-ttu-id="29125-111">La `ICeeFileGen` objeto se usa para crear de common language runtime (CLR) los archivos de archivo ejecutable portable (PE).</span><span class="sxs-lookup"><span data-stu-id="29125-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="29125-112">Llame a la [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) función para destruir el `ICeeFileGen` objeto cuando termine.</span><span class="sxs-lookup"><span data-stu-id="29125-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29125-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="29125-113">Requirements</span></span>  
 <span data-ttu-id="29125-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29125-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29125-115">**Encabezado**: ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="29125-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="29125-116">**Biblioteca:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="29125-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="29125-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29125-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29125-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="29125-118">See also</span></span>

- [<span data-ttu-id="29125-119">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="29125-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
