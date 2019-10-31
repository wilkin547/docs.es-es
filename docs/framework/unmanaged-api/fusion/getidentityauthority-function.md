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
ms.openlocfilehash: acb80f3cc199d4d9f774cb3898335d26fe44b807
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127149"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="02b7b-102">GetIdentityAuthority (Función)</span><span class="sxs-lookup"><span data-stu-id="02b7b-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="02b7b-103">Obtiene un puntero a una instancia de [iidentityauthority (](iidentityauthority-interface.md) que administra las claves de los objetos de código.</span><span class="sxs-lookup"><span data-stu-id="02b7b-103">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02b7b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02b7b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="02b7b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="02b7b-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="02b7b-106">enuncia Puntero `IIdentityAuthority` devuelto.</span><span class="sxs-lookup"><span data-stu-id="02b7b-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02b7b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02b7b-107">Requirements</span></span>  
 <span data-ttu-id="02b7b-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02b7b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02b7b-109">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="02b7b-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="02b7b-110">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02b7b-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02b7b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="02b7b-111">See also</span></span>

- [<span data-ttu-id="02b7b-112">IIdentityAuthority (interfaz)</span><span class="sxs-lookup"><span data-stu-id="02b7b-112">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)
- [<span data-ttu-id="02b7b-113">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="02b7b-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
