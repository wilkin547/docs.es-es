---
title: ICorThreadpool::CorRegisterWaitForSingleObject (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorRegisterWaitForSingleObject
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegisterWaitForSingleObject
helpviewer_keywords:
- ICorThreadpool::CorRegisterWaitForSingleObject method [.NET Framework hosting]
- CorRegisterWaitForSingleObject method [.NET Framework hosting]
ms.assetid: cade1feb-71d2-43ed-85ca-7b2e9da12994
topic_type:
- apiref
ms.openlocfilehash: 8e251ade301ce3ed85f4483634eeae4ca135334a
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762726"
---
# <a name="icorthreadpoolcorregisterwaitforsingleobject-method"></a><span data-ttu-id="452c2-102">ICorThreadpool::CorRegisterWaitForSingleObject (Método)</span><span class="sxs-lookup"><span data-stu-id="452c2-102">ICorThreadpool::CorRegisterWaitForSingleObject Method</span></span>
<span data-ttu-id="452c2-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="452c2-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="452c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="452c2-104">Syntax</span></span>  
  
```cpp  
HRESULT CorRegisterWaitForSingleObject (  
    [in]  HANDLE*             phNewWaitObject,  
    [in]  HANDLE              hWaitObject,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Context,  
    [in]  ULONG               timeout,  
    [in]  BOOL                executeOnlyOnce,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="452c2-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="452c2-105">Requirements</span></span>  
 <span data-ttu-id="452c2-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="452c2-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="452c2-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="452c2-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="452c2-108">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="452c2-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="452c2-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="452c2-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="452c2-110">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="452c2-110">See also</span></span>

- [<span data-ttu-id="452c2-111">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="452c2-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
