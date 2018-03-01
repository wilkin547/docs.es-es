---
title: "StrongNameKeyInstall (Función)"
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
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9a8dbc84f375b7bbbad47971936650d81c5c63df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="ad017-102">StrongNameKeyInstall (Función)</span><span class="sxs-lookup"><span data-stu-id="ad017-102">StrongNameKeyInstall Function</span></span>
<span data-ttu-id="ad017-103">Importa un par de claves pública/privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="ad017-103">Imports a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="ad017-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="ad017-104">This function has been deprecated.</span></span> <span data-ttu-id="ad017-105">Use la [ICLRStrongName:: StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ad017-105">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad017-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad017-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad017-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ad017-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="ad017-108">[in] Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="ad017-108">[in] The name of the key container.</span></span> <span data-ttu-id="ad017-109">`wszKeyContainer`debe ser una cadena no vacía.</span><span class="sxs-lookup"><span data-stu-id="ad017-109">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="ad017-110">[in] El par de claves binario.</span><span class="sxs-lookup"><span data-stu-id="ad017-110">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="ad017-111">[in] El tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="ad017-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad017-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ad017-112">Return Value</span></span>  
 <span data-ttu-id="ad017-113">`true`Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ad017-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad017-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad017-114">Remarks</span></span>  
 <span data-ttu-id="ad017-115">Use la [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) función para eliminar el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="ad017-115">Use the [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) function to delete the key container.</span></span>  
  
 <span data-ttu-id="ad017-116">Si el `StrongNameKeyInstall` función no se completan correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="ad017-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad017-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad017-117">Requirements</span></span>  
 <span data-ttu-id="ad017-118">**Plataformas:** WindSee [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad017-118">**Platforms:** WindSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad017-119">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="ad017-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ad017-120">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ad017-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ad017-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad017-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad017-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad017-122">See Also</span></span>  
 [<span data-ttu-id="ad017-123">StrongNameKeyInstall (método)</span><span class="sxs-lookup"><span data-stu-id="ad017-123">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="ad017-124">StrongNameKeyDelete (método)</span><span class="sxs-lookup"><span data-stu-id="ad017-124">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="ad017-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad017-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
