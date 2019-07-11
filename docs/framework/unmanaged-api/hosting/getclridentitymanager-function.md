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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ea4947582e4e8bfdb6873a90c5284e9ae9d8a62
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736245"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="8f802-102">GetCLRIdentityManager (Función)</span><span class="sxs-lookup"><span data-stu-id="8f802-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="8f802-103">Obtiene un puntero a una interfaz que permite que common language runtime (CLR) para administrar las identidades.</span><span class="sxs-lookup"><span data-stu-id="8f802-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="8f802-104">Esta función está desusada en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="8f802-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f802-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f802-105">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f802-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f802-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="8f802-107">[in] Un `REFIID` (un identificador de interfaz) que especifica la interfaz que desea obtener.</span><span class="sxs-lookup"><span data-stu-id="8f802-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="8f802-108">Este valor debe ser IID_ICLRAssemblyIdentityManager o IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="8f802-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="8f802-109">[out] Un puntero a la dirección de uno de ellos un [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) o un [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="8f802-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f802-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8f802-110">Remarks</span></span>  
 <span data-ttu-id="8f802-111">Llame a la [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) función para obtener un puntero a la `GetCLRIdentityManager` función.</span><span class="sxs-lookup"><span data-stu-id="8f802-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f802-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f802-112">Requirements</span></span>  
 <span data-ttu-id="8f802-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f802-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f802-114">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8f802-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f802-115">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="8f802-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="8f802-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f802-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f802-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f802-117">See also</span></span>

- [<span data-ttu-id="8f802-118">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="8f802-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
