---
title: "GetCLRIdentityManager (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCLRIdentityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: GetCLRIdentityManager
helpviewer_keywords: GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ddc0395b6fd659ecd6a26a3132fccc65bbb961fe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="92445-102">GetCLRIdentityManager (Función)</span><span class="sxs-lookup"><span data-stu-id="92445-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="92445-103">Obtiene un puntero a una interfaz que permite que common language runtime (CLR) para administrar identidades.</span><span class="sxs-lookup"><span data-stu-id="92445-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="92445-104">Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92445-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92445-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92445-105">Syntax</span></span>  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92445-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="92445-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="92445-107">[in] A `REFIID` (un identificador de interfaz) que especifica qué interfaz va a obtener.</span><span class="sxs-lookup"><span data-stu-id="92445-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="92445-108">Este valor debe ser IID_ICLRAssemblyIdentityManager o IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="92445-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="92445-109">[out] Un puntero a la dirección de uno de ellos un [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) o un [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="92445-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92445-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="92445-110">Remarks</span></span>  
 <span data-ttu-id="92445-111">Llame a la [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) función para obtener un puntero a la `GetCLRIdentityManager` (función).</span><span class="sxs-lookup"><span data-stu-id="92445-111">Call the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92445-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92445-112">Requirements</span></span>  
 <span data-ttu-id="92445-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92445-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92445-114">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="92445-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="92445-115">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="92445-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="92445-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92445-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92445-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="92445-117">See Also</span></span>  
 [<span data-ttu-id="92445-118">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="92445-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
