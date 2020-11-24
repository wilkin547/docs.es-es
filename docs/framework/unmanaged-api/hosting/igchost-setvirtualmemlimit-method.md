---
title: IGCHost::SetVirtualMemLimit (Método)
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
ms.openlocfilehash: 9898b760edbb149afcd6bf957a30d0a47287485b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687826"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="73d94-102">IGCHost::SetVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="73d94-102">IGCHost::SetVirtualMemLimit Method</span></span>

<span data-ttu-id="73d94-103">Establece el tamaño máximo de la memoria virtual del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="73d94-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73d94-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73d94-104">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73d94-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="73d94-105">Parameters</span></span>  

 `sztMaxVirtualMemMB`  
 <span data-ttu-id="73d94-106">de Tamaño máximo, en megabytes, de la memoria virtual del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="73d94-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73d94-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="73d94-107">Remarks</span></span>  

 <span data-ttu-id="73d94-108">El tamaño máximo de la memoria virtual del tiempo de ejecución se puede cambiar dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="73d94-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73d94-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73d94-109">Requirements</span></span>  

 <span data-ttu-id="73d94-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73d94-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73d94-111">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="73d94-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="73d94-112">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73d94-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73d94-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73d94-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73d94-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73d94-114">See also</span></span>

- [<span data-ttu-id="73d94-115">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="73d94-115">IGCHost Interface</span></span>](igchost-interface.md)
