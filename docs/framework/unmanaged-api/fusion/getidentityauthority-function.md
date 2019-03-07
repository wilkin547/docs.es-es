---
title: GetIdentityAuthority (Función)
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09d6284d7042dfebee004c4cb18d8ef3752c325c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496994"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="98998-102">GetIdentityAuthority (Función)</span><span class="sxs-lookup"><span data-stu-id="98998-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="98998-103">Obtiene un puntero a un [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instancia que administra las claves para los objetos de código.</span><span class="sxs-lookup"><span data-stu-id="98998-103">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98998-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98998-104">Syntax</span></span>  
  
```  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="98998-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98998-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="98998-106">[out] El valor devuelto `IIdentityAuthority` puntero.</span><span class="sxs-lookup"><span data-stu-id="98998-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98998-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98998-107">Requirements</span></span>  
 <span data-ttu-id="98998-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98998-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98998-109">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="98998-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="98998-110">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98998-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98998-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="98998-111">See also</span></span>
- [<span data-ttu-id="98998-112">IIdentityAuthority (interfaz)</span><span class="sxs-lookup"><span data-stu-id="98998-112">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)
- [<span data-ttu-id="98998-113">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="98998-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
