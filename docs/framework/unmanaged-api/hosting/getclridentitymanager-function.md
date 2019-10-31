---
title: GetCLRIdentityManager (Función)
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
ms.openlocfilehash: 3c6def32c63e3557a4de72baf7b1c3e67feb4891
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136527"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="2a6e2-102">GetCLRIdentityManager (Función)</span><span class="sxs-lookup"><span data-stu-id="2a6e2-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="2a6e2-103">Obtiene un puntero a una interfaz que permite al Common Language Runtime (CLR) administrar las identidades.</span><span class="sxs-lookup"><span data-stu-id="2a6e2-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="2a6e2-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="2a6e2-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a6e2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a6e2-105">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a6e2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a6e2-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="2a6e2-107">de `REFIID` (identificador de interfaz) que especifica la interfaz que se va a obtener.</span><span class="sxs-lookup"><span data-stu-id="2a6e2-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="2a6e2-108">Este valor debe ser IID_ICLRAssemblyIdentityManager o IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="2a6e2-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="2a6e2-109">enuncia Puntero a la dirección de un objeto [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) o [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2a6e2-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a6e2-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a6e2-110">Remarks</span></span>  
 <span data-ttu-id="2a6e2-111">Llame a la función [GetRealProcAddress (](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) para obtener un puntero a la función `GetCLRIdentityManager`.</span><span class="sxs-lookup"><span data-stu-id="2a6e2-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a6e2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a6e2-112">Requirements</span></span>  
 <span data-ttu-id="2a6e2-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a6e2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a6e2-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2a6e2-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a6e2-115">**Biblioteca:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="2a6e2-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="2a6e2-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a6e2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a6e2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a6e2-117">See also</span></span>

- [<span data-ttu-id="2a6e2-118">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="2a6e2-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
