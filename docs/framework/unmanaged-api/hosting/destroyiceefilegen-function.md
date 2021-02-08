---
description: 'Más información acerca de: DestroyICeeFileGen ((función)'
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
ms.openlocfilehash: 14ae990999247b90f16b10115dea3408b965a04a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785658"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="cc5fc-103">DestroyICeeFileGen (Función)</span><span class="sxs-lookup"><span data-stu-id="cc5fc-103">DestroyICeeFileGen Function</span></span>

<span data-ttu-id="cc5fc-104">Destruye un objeto [ICeeFileGen](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="cc5fc-104">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="cc5fc-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="cc5fc-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc5fc-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc5fc-106">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc5fc-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cc5fc-107">Parameters</span></span>  

 `ceeFileGen`  
 <span data-ttu-id="cc5fc-108">de `ICeeFileGen` Objeto que se va a destruir.</span><span class="sxs-lookup"><span data-stu-id="cc5fc-108">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc5fc-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cc5fc-109">Return Value</span></span>  

 <span data-ttu-id="cc5fc-110">Este método devuelve los códigos de error COM estándar.</span><span class="sxs-lookup"><span data-stu-id="cc5fc-110">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc5fc-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cc5fc-111">Remarks</span></span>  

 <span data-ttu-id="cc5fc-112">`DestroyICeeFileGen` destruye el `ICeeFileGen` objeto creado por la función [CreateICeeFileGen (](createiceefilegen-function.md) .</span><span class="sxs-lookup"><span data-stu-id="cc5fc-112">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc5fc-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc5fc-113">Requirements</span></span>  

 <span data-ttu-id="cc5fc-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc5fc-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc5fc-115">**Encabezado:** ICeeFileGen. h</span><span class="sxs-lookup"><span data-stu-id="cc5fc-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="cc5fc-116">**Biblioteca:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="cc5fc-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="cc5fc-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc5fc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc5fc-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc5fc-118">See also</span></span>

- [<span data-ttu-id="cc5fc-119">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="cc5fc-119">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
