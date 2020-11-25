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
ms.openlocfilehash: 9d1196749e033c71b0c8923d0325eb4886122d1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733664"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="c994d-102">GetCLRIdentityManager (Función)</span><span class="sxs-lookup"><span data-stu-id="c994d-102">GetCLRIdentityManager Function</span></span>

<span data-ttu-id="c994d-103">Obtiene un puntero a una interfaz que permite al Common Language Runtime (CLR) administrar las identidades.</span><span class="sxs-lookup"><span data-stu-id="c994d-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="c994d-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c994d-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c994d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c994d-105">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c994d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c994d-106">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="c994d-107">de Un `REFIID` (identificador de interfaz) que especifica la interfaz que se va a obtener.</span><span class="sxs-lookup"><span data-stu-id="c994d-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="c994d-108">Este valor debe ser IID_ICLRAssemblyIdentityManager o IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="c994d-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="c994d-109">enuncia Puntero a la dirección de un objeto [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) o [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c994d-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c994d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c994d-110">Remarks</span></span>  

 <span data-ttu-id="c994d-111">Llame a la función [GetRealProcAddress (](getrealprocaddress-function.md) para obtener un puntero a la `GetCLRIdentityManager` función.</span><span class="sxs-lookup"><span data-stu-id="c994d-111">Call the [GetRealProcAddress](getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c994d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c994d-112">Requirements</span></span>  

 <span data-ttu-id="c994d-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c994d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c994d-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c994d-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c994d-115">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="c994d-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="c994d-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c994d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c994d-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c994d-117">See also</span></span>

- [<span data-ttu-id="c994d-118">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="c994d-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
