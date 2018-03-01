---
title: "StrongNameKeyDelete (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d3acd8ae5f330e23642a679962a04ccb4f7e8ec6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="82d3b-102">StrongNameKeyDelete (Función)</span><span class="sxs-lookup"><span data-stu-id="82d3b-102">StrongNameKeyDelete Function</span></span>
<span data-ttu-id="82d3b-103">Elimina el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="82d3b-103">Deletes the specified key container.</span></span>  
  
 <span data-ttu-id="82d3b-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="82d3b-104">This function has been deprecated.</span></span> <span data-ttu-id="82d3b-105">Use la [ICLRStrongName:: StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="82d3b-105">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82d3b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82d3b-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82d3b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="82d3b-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="82d3b-108">[in] Nombre del contenedor de claves para eliminar.</span><span class="sxs-lookup"><span data-stu-id="82d3b-108">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82d3b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="82d3b-109">Return Value</span></span>  
 <span data-ttu-id="82d3b-110">`true`Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="82d3b-110">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82d3b-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="82d3b-111">Remarks</span></span>  
 <span data-ttu-id="82d3b-112">Use la [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) función para importar un par de claves pública/privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="82d3b-112">Use the [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) function to importa a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="82d3b-113">Si el `StrongNameKeyDelete` función no se completan correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="82d3b-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82d3b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82d3b-114">Requirements</span></span>  
 <span data-ttu-id="82d3b-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82d3b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82d3b-116">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="82d3b-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="82d3b-117">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="82d3b-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="82d3b-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82d3b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82d3b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="82d3b-119">See Also</span></span>  
 [<span data-ttu-id="82d3b-120">StrongNameKeyDelete (método)</span><span class="sxs-lookup"><span data-stu-id="82d3b-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="82d3b-121">StrongNameKeyInstall (método)</span><span class="sxs-lookup"><span data-stu-id="82d3b-121">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="82d3b-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="82d3b-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
