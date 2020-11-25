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
ms.openlocfilehash: 5e731ac1c652b8b4505073a3a10463ae0ce21ac0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724499"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="11c24-102">GetAppIdAuthority (Función)</span><span class="sxs-lookup"><span data-stu-id="11c24-102">GetAppIdAuthority Function</span></span>

<span data-ttu-id="11c24-103">Obtiene un puntero a una instancia de [iappidauthority (](iappidauthority-interface.md) que administra las claves de las identidades y referencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="11c24-103">Gets a pointer to an [IAppIdAuthority](iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11c24-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11c24-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="11c24-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11c24-105">Parameters</span></span>  

 `ppIAppIdAuthority`  
 <span data-ttu-id="11c24-106">enuncia Puntero devuelto `IAppIdAuthority` .</span><span class="sxs-lookup"><span data-stu-id="11c24-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11c24-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11c24-107">Requirements</span></span>  

 <span data-ttu-id="11c24-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11c24-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11c24-109">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="11c24-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="11c24-110">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11c24-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11c24-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11c24-111">See also</span></span>

- [<span data-ttu-id="11c24-112">IAppIdAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="11c24-112">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)
- [<span data-ttu-id="11c24-113">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="11c24-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
