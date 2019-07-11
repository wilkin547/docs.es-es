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
ms.openlocfilehash: c5e8dd4a9dbf301b0910eda220513e9a3ffdc1cb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778637"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="12c9a-102">GetIdentityAuthority (Función)</span><span class="sxs-lookup"><span data-stu-id="12c9a-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="12c9a-103">Obtiene un puntero a un [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instancia que administra las claves para los objetos de código.</span><span class="sxs-lookup"><span data-stu-id="12c9a-103">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12c9a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12c9a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="12c9a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="12c9a-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="12c9a-106">[out] El valor devuelto `IIdentityAuthority` puntero.</span><span class="sxs-lookup"><span data-stu-id="12c9a-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12c9a-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="12c9a-107">Requirements</span></span>  
 <span data-ttu-id="12c9a-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12c9a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12c9a-109">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="12c9a-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="12c9a-110">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12c9a-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12c9a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="12c9a-111">See also</span></span>

- [<span data-ttu-id="12c9a-112">IIdentityAuthority (interfaz)</span><span class="sxs-lookup"><span data-stu-id="12c9a-112">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)
- [<span data-ttu-id="12c9a-113">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="12c9a-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
