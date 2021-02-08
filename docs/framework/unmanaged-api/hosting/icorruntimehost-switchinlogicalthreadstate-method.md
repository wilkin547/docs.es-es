---
description: 'Más información sobre: ICorRuntimeHost:: SwitchInLogicalThreadState ((método)'
title: ICorRuntimeHost::SwitchInLogicalThreadState (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
ms.openlocfilehash: 3e375379cc5d6af7c3a8fb8d64a40a389e0f9dcc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789572"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="d67c9-103">ICorRuntimeHost::SwitchInLogicalThreadState (Método)</span><span class="sxs-lookup"><span data-stu-id="d67c9-103">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>

<span data-ttu-id="d67c9-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="d67c9-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d67c9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d67c9-105">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d67c9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d67c9-106">Parameters</span></span>  

 `pFiberCookie`  
 <span data-ttu-id="d67c9-107">de Cookie que indica la fibra que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="d67c9-107">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d67c9-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d67c9-108">Requirements</span></span>  

 <span data-ttu-id="d67c9-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d67c9-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d67c9-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d67c9-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d67c9-111">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d67c9-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d67c9-112">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="d67c9-112">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d67c9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d67c9-113">See also</span></span>

- [<span data-ttu-id="d67c9-114">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d67c9-114">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
