---
title: ITypeName::GetModifiers (Método)
ms.date: 03/30/2017
api_name:
- ITypeName.GetModifiers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type:
- apiref
ms.openlocfilehash: 8544b8d7b1f23853465bbb2aea697dfe021d77f2
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842184"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="99dc1-102">ITypeName::GetModifiers (Método)</span><span class="sxs-lookup"><span data-stu-id="99dc1-102">ITypeName::GetModifiers Method</span></span>
<span data-ttu-id="99dc1-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="99dc1-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99dc1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99dc1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="99dc1-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99dc1-105">Requirements</span></span>  
 <span data-ttu-id="99dc1-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99dc1-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99dc1-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="99dc1-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99dc1-108">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="99dc1-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99dc1-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99dc1-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99dc1-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="99dc1-110">See also</span></span>

- [<span data-ttu-id="99dc1-111">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="99dc1-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
