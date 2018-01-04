---
title: "ICLRStrongName::StrongNameKeyInstall (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyInstall
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df1bdb5d6d6018855cb76b48d58e557a61288a51
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="7bc3c-102">ICLRStrongName::StrongNameKeyInstall (Método)</span><span class="sxs-lookup"><span data-stu-id="7bc3c-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="7bc3c-103">Importa un par de claves pública/privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="7bc3c-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bc3c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7bc3c-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7bc3c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7bc3c-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="7bc3c-106">[in] Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="7bc3c-106">[in] The name of the key container.</span></span> <span data-ttu-id="7bc3c-107">`wszKeyContainer`debe ser una cadena no vacía.</span><span class="sxs-lookup"><span data-stu-id="7bc3c-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="7bc3c-108">[in] El par de claves binario.</span><span class="sxs-lookup"><span data-stu-id="7bc3c-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="7bc3c-109">[in] El tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="7bc3c-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7bc3c-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7bc3c-110">Return Value</span></span>  
 <span data-ttu-id="7bc3c-111">`S_OK`Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="7bc3c-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bc3c-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7bc3c-112">Remarks</span></span>  
 <span data-ttu-id="7bc3c-113">Use la [ICLRStrongName:: StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) método para eliminar el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="7bc3c-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bc3c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7bc3c-114">Requirements</span></span>  
 <span data-ttu-id="7bc3c-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bc3c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bc3c-116">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7bc3c-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7bc3c-117">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7bc3c-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7bc3c-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bc3c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bc3c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bc3c-119">See Also</span></span>  
 [<span data-ttu-id="7bc3c-120">StrongNameKeyDelete (método)</span><span class="sxs-lookup"><span data-stu-id="7bc3c-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="7bc3c-121">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7bc3c-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
