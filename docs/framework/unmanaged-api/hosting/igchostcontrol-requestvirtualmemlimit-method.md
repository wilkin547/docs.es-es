---
description: 'Más información sobre: Igchostcontrol (:: Requestvirtualmemlimit ((método)'
title: IGCHostControl::RequestVirtualMemLimit (Método)
ms.date: 03/30/2017
api_name:
- IGCHostControl.RequestVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type:
- apiref
ms.openlocfilehash: b0ee22671b63be0ed0d23ebb103a6a5a7ca9f2b9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709430"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="09950-103">IGCHostControl::RequestVirtualMemLimit (Método)</span><span class="sxs-lookup"><span data-stu-id="09950-103">IGCHostControl::RequestVirtualMemLimit Method</span></span>

<span data-ttu-id="09950-104">Solicita al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="09950-104">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09950-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09950-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09950-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09950-106">Parameters</span></span>  

 `sztMaxVirtualMemMB`  
 <span data-ttu-id="09950-107">de Tamaño solicitado de memoria que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="09950-107">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="09950-108">[in, out] Puntero al tamaño real de la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="09950-108">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09950-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09950-109">Requirements</span></span>  

 <span data-ttu-id="09950-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09950-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09950-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="09950-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09950-112">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="09950-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09950-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09950-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09950-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="09950-114">See also</span></span>

- [<span data-ttu-id="09950-115">IGCHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09950-115">IGCHostControl Interface</span></span>](igchostcontrol-interface.md)
