---
description: 'Más información acerca de: GetIdentityAuthority ((función)'
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
ms.openlocfilehash: 5126aa9b319af41f7ecd30845a9f74ba69016588
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761003"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="fa0de-103">GetIdentityAuthority (Función)</span><span class="sxs-lookup"><span data-stu-id="fa0de-103">GetIdentityAuthority Function</span></span>

<span data-ttu-id="fa0de-104">Obtiene un puntero a una instancia de [iidentityauthority (](iidentityauthority-interface.md) que administra las claves de los objetos de código.</span><span class="sxs-lookup"><span data-stu-id="fa0de-104">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa0de-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa0de-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa0de-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa0de-106">Parameters</span></span>  

 `ppIIdentityAuthority`  
 <span data-ttu-id="fa0de-107">enuncia Puntero devuelto `IIdentityAuthority` .</span><span class="sxs-lookup"><span data-stu-id="fa0de-107">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa0de-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa0de-108">Requirements</span></span>  

 <span data-ttu-id="fa0de-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa0de-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa0de-110">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="fa0de-110">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="fa0de-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa0de-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa0de-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa0de-112">See also</span></span>

- [<span data-ttu-id="fa0de-113">IIdentityAuthority (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa0de-113">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)
- [<span data-ttu-id="fa0de-114">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="fa0de-114">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
