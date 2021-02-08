---
description: 'Más información acerca de: Iapartmentcallback (::D oCallback (método)'
title: IApartmentCallback::DoCallback (Método)
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
ms.openlocfilehash: 65b7f496f953f08e099bf13ef8212c7d6e1026ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785115"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="827a8-103">IApartmentCallback::DoCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="827a8-103">IApartmentCallback::DoCallback Method</span></span>

<span data-ttu-id="827a8-104">Ejecuta la función especificada dentro de un contenedor.</span><span class="sxs-lookup"><span data-stu-id="827a8-104">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="827a8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="827a8-105">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="827a8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="827a8-106">Parameters</span></span>  

 `pFunc`  
 <span data-ttu-id="827a8-107">de Puntero a la función que se va a ejecutar dentro del apartamento.</span><span class="sxs-lookup"><span data-stu-id="827a8-107">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="827a8-108">de Puntero al argumento de la función.</span><span class="sxs-lookup"><span data-stu-id="827a8-108">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="827a8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="827a8-109">Requirements</span></span>  

 <span data-ttu-id="827a8-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="827a8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="827a8-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="827a8-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="827a8-112">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="827a8-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="827a8-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="827a8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="827a8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="827a8-114">See also</span></span>

- [<span data-ttu-id="827a8-115">IApartmentCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="827a8-115">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)
