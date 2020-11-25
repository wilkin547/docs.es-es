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
ms.openlocfilehash: e9631211993afbfe968c7122828251746f15c3f6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732137"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="52731-102">GetIdentityAuthority (Función)</span><span class="sxs-lookup"><span data-stu-id="52731-102">GetIdentityAuthority Function</span></span>

<span data-ttu-id="52731-103">Obtiene un puntero a una instancia de [iidentityauthority (](iidentityauthority-interface.md) que administra las claves de los objetos de código.</span><span class="sxs-lookup"><span data-stu-id="52731-103">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52731-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52731-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="52731-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52731-105">Parameters</span></span>  

 `ppIIdentityAuthority`  
 <span data-ttu-id="52731-106">enuncia Puntero devuelto `IIdentityAuthority` .</span><span class="sxs-lookup"><span data-stu-id="52731-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52731-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52731-107">Requirements</span></span>  

 <span data-ttu-id="52731-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52731-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52731-109">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="52731-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="52731-110">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52731-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52731-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52731-111">See also</span></span>

- [<span data-ttu-id="52731-112">IIdentityAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="52731-112">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)
- [<span data-ttu-id="52731-113">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="52731-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
