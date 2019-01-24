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
ms.openlocfilehash: f40100be3ab05c0c8e8a55d48494569424e88371
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637273"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="72ee7-102">GetCLRIdentityManager (Función)</span><span class="sxs-lookup"><span data-stu-id="72ee7-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="72ee7-103">Obtiene un puntero a una interfaz que permite que common language runtime (CLR) para administrar las identidades.</span><span class="sxs-lookup"><span data-stu-id="72ee7-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="72ee7-104">Esta función está en desuso en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72ee7-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72ee7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72ee7-105">Syntax</span></span>  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72ee7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72ee7-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="72ee7-107">[in] Un `REFIID` (un identificador de interfaz) que especifica la interfaz que desea obtener.</span><span class="sxs-lookup"><span data-stu-id="72ee7-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="72ee7-108">Este valor debe ser IID_ICLRAssemblyIdentityManager o IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="72ee7-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="72ee7-109">[out] Un puntero a la dirección de uno de ellos un [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) o un [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="72ee7-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72ee7-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="72ee7-110">Remarks</span></span>  
 <span data-ttu-id="72ee7-111">Llame a la [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) función para obtener un puntero a la `GetCLRIdentityManager` función.</span><span class="sxs-lookup"><span data-stu-id="72ee7-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72ee7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72ee7-112">Requirements</span></span>  
 <span data-ttu-id="72ee7-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72ee7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72ee7-114">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="72ee7-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="72ee7-115">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="72ee7-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="72ee7-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72ee7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72ee7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="72ee7-117">See also</span></span>
- [<span data-ttu-id="72ee7-118">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="72ee7-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
