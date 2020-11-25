---
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
ms.openlocfilehash: 32b6d2c05a96658ab2b8ec1df288d2be05bb947f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730674"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="d2cb5-102">IObjectHandle::Unwrap (Método)</span><span class="sxs-lookup"><span data-stu-id="d2cb5-102">IObjectHandle::Unwrap Method</span></span>

<span data-ttu-id="d2cb5-103">Desencapsula un objeto de cálculo de referencias por valor desde el direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="d2cb5-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2cb5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2cb5-104">Syntax</span></span>  
  
```cpp  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2cb5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d2cb5-105">Parameters</span></span>  

 `ppv`  
 <span data-ttu-id="d2cb5-106">enuncia Puntero al objeto que se va a desempaquetar.</span><span class="sxs-lookup"><span data-stu-id="d2cb5-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2cb5-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2cb5-107">Requirements</span></span>  

 <span data-ttu-id="d2cb5-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2cb5-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2cb5-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d2cb5-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2cb5-110">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2cb5-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2cb5-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2cb5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
