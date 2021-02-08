---
description: 'Más información sobre: ICorRuntimeHost:: Switchoutlogicalthreadstate ((método)'
title: ICorRuntimeHost::SwitchOutLogicalThreadState (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchOutLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]
- SwitchOutLogicalThreadState method [.NET Framework hosting]
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
topic_type:
- apiref
ms.openlocfilehash: b4190ebe6b2c260f85afd8dd17127d0c63dca6c8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799452"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="ef63f-103">ICorRuntimeHost::SwitchOutLogicalThreadState (Método)</span><span class="sxs-lookup"><span data-stu-id="ef63f-103">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>

<span data-ttu-id="ef63f-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="ef63f-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef63f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef63f-105">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef63f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef63f-106">Parameters</span></span>  

 `pFiberCookie`  
 <span data-ttu-id="ef63f-107">enuncia Cookie que indica la fibra que se va a desactivar.</span><span class="sxs-lookup"><span data-stu-id="ef63f-107">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef63f-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef63f-108">Requirements</span></span>  

 <span data-ttu-id="ef63f-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef63f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef63f-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ef63f-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef63f-111">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef63f-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef63f-112">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="ef63f-112">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef63f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef63f-113">See also</span></span>

- [<span data-ttu-id="ef63f-114">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef63f-114">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
