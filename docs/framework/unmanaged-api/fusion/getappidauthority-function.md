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
ms.openlocfilehash: 8471610008bee02c7cc4e7654b21d6aca5dcf53a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796276"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="6eee9-102">GetAppIdAuthority (Función)</span><span class="sxs-lookup"><span data-stu-id="6eee9-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="6eee9-103">Obtiene un puntero a una instancia de [iappidauthority (](iappidauthority-interface.md) que administra las claves de las identidades y referencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6eee9-103">Gets a pointer to an [IAppIdAuthority](iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eee9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6eee9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="6eee9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6eee9-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="6eee9-106">enuncia Puntero devuelto `IAppIdAuthority` .</span><span class="sxs-lookup"><span data-stu-id="6eee9-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6eee9-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6eee9-107">Requirements</span></span>  
 <span data-ttu-id="6eee9-108">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6eee9-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6eee9-109">**Encabezado**: Isolation. h</span><span class="sxs-lookup"><span data-stu-id="6eee9-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="6eee9-110">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6eee9-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eee9-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6eee9-111">See also</span></span>

- [<span data-ttu-id="6eee9-112">IAppIdAuthority (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6eee9-112">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)
- [<span data-ttu-id="6eee9-113">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="6eee9-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
