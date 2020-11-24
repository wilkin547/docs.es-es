---
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
ms.openlocfilehash: a4590bcd96226a713ff5535a8bc802c2116f862a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690140"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="67378-102">ICorRuntimeHost::SwitchInLogicalThreadState (Método)</span><span class="sxs-lookup"><span data-stu-id="67378-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>

<span data-ttu-id="67378-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="67378-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67378-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67378-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67378-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="67378-105">Parameters</span></span>  

 `pFiberCookie`  
 <span data-ttu-id="67378-106">de Cookie que indica la fibra que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="67378-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67378-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67378-107">Requirements</span></span>  

 <span data-ttu-id="67378-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67378-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67378-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="67378-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67378-110">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67378-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67378-111">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="67378-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67378-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67378-112">See also</span></span>

- [<span data-ttu-id="67378-113">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="67378-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
