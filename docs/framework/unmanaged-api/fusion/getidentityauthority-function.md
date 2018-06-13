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
ms.openlocfilehash: eae17c2dbccb4296d7542c60a30b341f1ad67f88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429571"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="3e491-102">GetIdentityAuthority (Función)</span><span class="sxs-lookup"><span data-stu-id="3e491-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="3e491-103">Obtiene un puntero a un [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instancia que administra las claves para los objetos de código.</span><span class="sxs-lookup"><span data-stu-id="3e491-103">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e491-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e491-104">Syntax</span></span>  
  
```  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e491-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3e491-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="3e491-106">[out] El valor devuelto `IIdentityAuthority` puntero.</span><span class="sxs-lookup"><span data-stu-id="3e491-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e491-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e491-107">Requirements</span></span>  
 <span data-ttu-id="3e491-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e491-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e491-109">**Encabezado:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="3e491-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="3e491-110">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e491-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e491-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e491-111">See Also</span></span>  
 [<span data-ttu-id="3e491-112">IIdentityAuthority (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e491-112">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 [<span data-ttu-id="3e491-113">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="3e491-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
