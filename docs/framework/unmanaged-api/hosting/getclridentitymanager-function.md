---
description: 'Más información acerca de: Getclridentitymanager ((función)'
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
ms.openlocfilehash: 483cf0499fa162da4c89e350198a5609f9f1bab6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785372"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="e5990-103">GetCLRIdentityManager (Función)</span><span class="sxs-lookup"><span data-stu-id="e5990-103">GetCLRIdentityManager Function</span></span>

<span data-ttu-id="e5990-104">Obtiene un puntero a una interfaz que permite al Common Language Runtime (CLR) administrar las identidades.</span><span class="sxs-lookup"><span data-stu-id="e5990-104">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="e5990-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e5990-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5990-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5990-106">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5990-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e5990-107">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="e5990-108">de Un `REFIID` (identificador de interfaz) que especifica la interfaz que se va a obtener.</span><span class="sxs-lookup"><span data-stu-id="e5990-108">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="e5990-109">Este valor debe ser IID_ICLRAssemblyIdentityManager o IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="e5990-109">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="e5990-110">enuncia Puntero a la dirección de un objeto [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) o [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e5990-110">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5990-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e5990-111">Remarks</span></span>  

 <span data-ttu-id="e5990-112">Llame a la función [GetRealProcAddress (](getrealprocaddress-function.md) para obtener un puntero a la `GetCLRIdentityManager` función.</span><span class="sxs-lookup"><span data-stu-id="e5990-112">Call the [GetRealProcAddress](getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5990-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5990-113">Requirements</span></span>  

 <span data-ttu-id="e5990-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5990-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5990-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e5990-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5990-116">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="e5990-116">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="e5990-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5990-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5990-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5990-118">See also</span></span>

- [<span data-ttu-id="e5990-119">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="e5990-119">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
