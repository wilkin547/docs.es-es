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
ms.openlocfilehash: 454cfa2dd1b676f32649050625b1074fbd776d54
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673337"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="bd21e-102">CreateICeeFileGen (Función)</span><span class="sxs-lookup"><span data-stu-id="bd21e-102">CreateICeeFileGen Function</span></span>

<span data-ttu-id="bd21e-103">Crea un objeto [ICeeFileGen](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="bd21e-103">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="bd21e-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="bd21e-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd21e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd21e-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd21e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd21e-106">Parameters</span></span>  

 `ceeFileGen`  
 <span data-ttu-id="bd21e-107">enuncia Puntero a la dirección de un nuevo `ICeeFileGen` objeto.</span><span class="sxs-lookup"><span data-stu-id="bd21e-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd21e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bd21e-108">Return Value</span></span>  

 <span data-ttu-id="bd21e-109">Este método devuelve los códigos de error COM estándar.</span><span class="sxs-lookup"><span data-stu-id="bd21e-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd21e-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd21e-110">Remarks</span></span>  

 <span data-ttu-id="bd21e-111">El `ICeeFileGen` objeto se usa para crear archivos ejecutables portables (PE) de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="bd21e-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="bd21e-112">Llame a la función [DestroyICeeFileGen (](destroyiceefilegen-function.md) para destruir el `ICeeFileGen` objeto cuando termine.</span><span class="sxs-lookup"><span data-stu-id="bd21e-112">Call the [DestroyICeeFileGen](destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd21e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd21e-113">Requirements</span></span>  

 <span data-ttu-id="bd21e-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd21e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd21e-115">**Encabezado:** ICeeFileGen. h</span><span class="sxs-lookup"><span data-stu-id="bd21e-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="bd21e-116">**Biblioteca:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="bd21e-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="bd21e-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd21e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd21e-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd21e-118">See also</span></span>

- [<span data-ttu-id="bd21e-119">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="bd21e-119">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
