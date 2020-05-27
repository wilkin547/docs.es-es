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
ms.openlocfilehash: 0ff088731514b2da0d8b1fa51ef48d8b71d16528
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842236"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="b694e-102">IObjectHandle::Unwrap (Método)</span><span class="sxs-lookup"><span data-stu-id="b694e-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="b694e-103">Desencapsula un objeto de cálculo de referencias por valor desde el direccionamiento indirecto.</span><span class="sxs-lookup"><span data-stu-id="b694e-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b694e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b694e-104">Syntax</span></span>  
  
```cpp  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b694e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b694e-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="b694e-106">enuncia Puntero al objeto que se va a desempaquetar.</span><span class="sxs-lookup"><span data-stu-id="b694e-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b694e-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b694e-107">Requirements</span></span>  
 <span data-ttu-id="b694e-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b694e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b694e-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b694e-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b694e-110">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b694e-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b694e-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b694e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
