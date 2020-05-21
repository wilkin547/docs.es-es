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
ms.openlocfilehash: d830635b911fa5d80382e432f283c455c41af7a8
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762687"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="fd48f-102">ICorRuntimeHost::SwitchInLogicalThreadState (Método)</span><span class="sxs-lookup"><span data-stu-id="fd48f-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="fd48f-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="fd48f-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd48f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd48f-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd48f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd48f-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="fd48f-106">de Cookie que indica la fibra que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="fd48f-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd48f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd48f-107">Requirements</span></span>  
 <span data-ttu-id="fd48f-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd48f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd48f-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fd48f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd48f-110">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fd48f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd48f-111">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="fd48f-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd48f-112">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="fd48f-112">See also</span></span>

- [<span data-ttu-id="fd48f-113">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fd48f-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
