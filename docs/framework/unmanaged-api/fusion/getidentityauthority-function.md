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
ms.openlocfilehash: f29246bdb929c8eaf1ebce726164d5cd2269b9f1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796862"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="36dab-102">GetIdentityAuthority (Función)</span><span class="sxs-lookup"><span data-stu-id="36dab-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="36dab-103">Obtiene un puntero a una instancia de [iidentityauthority (](iidentityauthority-interface.md) que administra las claves de los objetos de código.</span><span class="sxs-lookup"><span data-stu-id="36dab-103">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36dab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36dab-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="36dab-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36dab-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="36dab-106">enuncia Puntero devuelto `IIdentityAuthority` .</span><span class="sxs-lookup"><span data-stu-id="36dab-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36dab-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36dab-107">Requirements</span></span>  
 <span data-ttu-id="36dab-108">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36dab-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36dab-109">**Encabezado**: Isolation. h</span><span class="sxs-lookup"><span data-stu-id="36dab-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="36dab-110">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36dab-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36dab-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="36dab-111">See also</span></span>

- [<span data-ttu-id="36dab-112">IIdentityAuthority (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36dab-112">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)
- [<span data-ttu-id="36dab-113">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="36dab-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
