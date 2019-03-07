---
title: GetAppIdAuthority (Función)
ms.date: 03/30/2017
api_name:
- GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetAppIdAuthority
helpviewer_keywords:
- GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 162341ee8cb27e5edc455207bbe094356c5167e7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466081"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="e0ce2-102">GetAppIdAuthority (Función)</span><span class="sxs-lookup"><span data-stu-id="e0ce2-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="e0ce2-103">Obtiene un puntero a un [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instancia que administra las claves para las identidades de aplicaciones y las referencias.</span><span class="sxs-lookup"><span data-stu-id="e0ce2-103">Gets a pointer to an [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0ce2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0ce2-104">Syntax</span></span>  
  
```  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0ce2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0ce2-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="e0ce2-106">[out] El valor devuelto `IAppIdAuthority` puntero.</span><span class="sxs-lookup"><span data-stu-id="e0ce2-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0ce2-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0ce2-107">Requirements</span></span>  
 <span data-ttu-id="e0ce2-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0ce2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0ce2-109">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="e0ce2-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e0ce2-110">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0ce2-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ce2-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0ce2-111">See also</span></span>
- [<span data-ttu-id="e0ce2-112">IAppIdAuthority (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0ce2-112">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)
- [<span data-ttu-id="e0ce2-113">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="e0ce2-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
