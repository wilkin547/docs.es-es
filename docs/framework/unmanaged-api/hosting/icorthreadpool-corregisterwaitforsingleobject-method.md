---
description: 'Más información sobre: ICorThreadpool:: Corregisterwaitforsingleobject ((método)'
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
ms.openlocfilehash: fdbb41f78f7aeb4a426de48e2da7616cfaecaa6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789559"
---
# <a name="icorthreadpoolcorregisterwaitforsingleobject-method"></a><span data-ttu-id="fb02c-103">ICorThreadpool::CorRegisterWaitForSingleObject (Método)</span><span class="sxs-lookup"><span data-stu-id="fb02c-103">ICorThreadpool::CorRegisterWaitForSingleObject Method</span></span>

<span data-ttu-id="fb02c-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="fb02c-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb02c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb02c-105">Syntax</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="fb02c-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb02c-106">Requirements</span></span>  

 <span data-ttu-id="fb02c-107">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb02c-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb02c-108">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fb02c-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb02c-109">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fb02c-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb02c-110">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb02c-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb02c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb02c-111">See also</span></span>

- [<span data-ttu-id="fb02c-112">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fb02c-112">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
