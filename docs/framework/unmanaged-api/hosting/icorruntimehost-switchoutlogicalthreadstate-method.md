---
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
ms.openlocfilehash: f32381dc40a744157e46780e59b83efd63e58dcb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762648"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="c0d74-102">ICorRuntimeHost::SwitchOutLogicalThreadState (Método)</span><span class="sxs-lookup"><span data-stu-id="c0d74-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="c0d74-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="c0d74-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0d74-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0d74-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0d74-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c0d74-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="c0d74-106">enuncia Cookie que indica la fibra que se va a desactivar.</span><span class="sxs-lookup"><span data-stu-id="c0d74-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0d74-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0d74-107">Requirements</span></span>  
 <span data-ttu-id="c0d74-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0d74-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0d74-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c0d74-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c0d74-110">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c0d74-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0d74-111">**Versión de .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="c0d74-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0d74-112">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="c0d74-112">See also</span></span>

- [<span data-ttu-id="c0d74-113">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c0d74-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
