---
description: 'Más información sobre: IGCHost:: SetVirtualMemLimit ((método)'
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
ms.openlocfilehash: 62cd9e2d84e51f0544e464bdbf49c50af8086546
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709443"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="313b8-103">IGCHost::SetVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="313b8-103">IGCHost::SetVirtualMemLimit Method</span></span>

<span data-ttu-id="313b8-104">Establece el tamaño máximo de la memoria virtual del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="313b8-104">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="313b8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="313b8-105">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="313b8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="313b8-106">Parameters</span></span>  

 `sztMaxVirtualMemMB`  
 <span data-ttu-id="313b8-107">de Tamaño máximo, en megabytes, de la memoria virtual del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="313b8-107">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="313b8-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="313b8-108">Remarks</span></span>  

 <span data-ttu-id="313b8-109">El tamaño máximo de la memoria virtual del tiempo de ejecución se puede cambiar dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="313b8-109">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="313b8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="313b8-110">Requirements</span></span>  

 <span data-ttu-id="313b8-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="313b8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="313b8-112">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="313b8-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="313b8-113">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="313b8-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="313b8-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="313b8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="313b8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="313b8-115">See also</span></span>

- [<span data-ttu-id="313b8-116">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="313b8-116">IGCHost Interface</span></span>](igchost-interface.md)
