---
description: 'Más información sobre: IObjectHandle (:: Unwrap (método)'
title: IObjectHandle::Unwrap (Método)
ms.date: 03/30/2017
api_name:
- IObjectHandle.Unwrap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type:
- apiref
ms.openlocfilehash: 3f791eaf52abd045d495fe15e868423e464fd27e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728332"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="89e8b-103">IObjectHandle::Unwrap (Método)</span><span class="sxs-lookup"><span data-stu-id="89e8b-103">IObjectHandle::Unwrap Method</span></span>

<span data-ttu-id="89e8b-104">Desencapsula un objeto de cálculo de referencias por valor desde el direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="89e8b-104">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89e8b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89e8b-105">Syntax</span></span>  
  
```cpp  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89e8b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89e8b-106">Parameters</span></span>  

 `ppv`  
 <span data-ttu-id="89e8b-107">enuncia Puntero al objeto que se va a desempaquetar.</span><span class="sxs-lookup"><span data-stu-id="89e8b-107">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89e8b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89e8b-108">Requirements</span></span>  

 <span data-ttu-id="89e8b-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89e8b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89e8b-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="89e8b-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89e8b-111">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89e8b-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89e8b-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89e8b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
