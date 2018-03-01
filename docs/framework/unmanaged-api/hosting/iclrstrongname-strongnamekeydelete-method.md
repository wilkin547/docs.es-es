---
title: "ICLRStrongName::StrongNameKeyDelete (Método)"
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
- ICLRStrongName.StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1b3a1d742ac2ad74d327afe4dce097d0f11e5cfe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="41853-102">ICLRStrongName::StrongNameKeyDelete (Método)</span><span class="sxs-lookup"><span data-stu-id="41853-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="41853-103">Elimina el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="41853-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41853-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41853-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41853-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41853-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="41853-106">[in] Nombre del contenedor de claves para eliminar.</span><span class="sxs-lookup"><span data-stu-id="41853-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41853-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="41853-107">Return Value</span></span>  
 <span data-ttu-id="41853-108">`S_OK`Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="41853-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41853-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="41853-109">Remarks</span></span>  
 <span data-ttu-id="41853-110">Use la [ICLRStrongName:: StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) método para importar un par de claves pública/privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="41853-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41853-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41853-111">Requirements</span></span>  
 <span data-ttu-id="41853-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41853-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41853-113">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="41853-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="41853-114">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="41853-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="41853-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41853-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41853-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="41853-116">See Also</span></span>  
 [<span data-ttu-id="41853-117">StrongNameKeyInstall (método)</span><span class="sxs-lookup"><span data-stu-id="41853-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="41853-118">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41853-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
