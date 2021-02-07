---
description: 'Más información acerca de: Getappidauthority ((función)'
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
ms.openlocfilehash: a0c2a7b754c2b014b189f96fd3c27347571cc0d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761075"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="e32ee-103">GetAppIdAuthority (Función)</span><span class="sxs-lookup"><span data-stu-id="e32ee-103">GetAppIdAuthority Function</span></span>

<span data-ttu-id="e32ee-104">Obtiene un puntero a una instancia de [iappidauthority (](iappidauthority-interface.md) que administra las claves de las identidades y referencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e32ee-104">Gets a pointer to an [IAppIdAuthority](iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e32ee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e32ee-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e32ee-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e32ee-106">Parameters</span></span>  

 `ppIAppIdAuthority`  
 <span data-ttu-id="e32ee-107">enuncia Puntero devuelto `IAppIdAuthority` .</span><span class="sxs-lookup"><span data-stu-id="e32ee-107">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e32ee-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e32ee-108">Requirements</span></span>  

 <span data-ttu-id="e32ee-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e32ee-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e32ee-110">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="e32ee-110">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e32ee-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e32ee-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e32ee-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e32ee-112">See also</span></span>

- [<span data-ttu-id="e32ee-113">IAppIdAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e32ee-113">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)
- [<span data-ttu-id="e32ee-114">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="e32ee-114">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
