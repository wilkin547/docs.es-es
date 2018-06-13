---
title: StrongNameKeyInstall (Función)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b6760a6418533f5c8f6cec815d86b4cff68aab1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460086"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="21d74-102">StrongNameKeyInstall (Función)</span><span class="sxs-lookup"><span data-stu-id="21d74-102">StrongNameKeyInstall Function</span></span>
<span data-ttu-id="21d74-103">Importa un par de claves pública/privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="21d74-103">Imports a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="21d74-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="21d74-104">This function has been deprecated.</span></span> <span data-ttu-id="21d74-105">Use la [ICLRStrongName:: StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="21d74-105">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21d74-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21d74-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="21d74-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="21d74-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="21d74-108">[in] Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="21d74-108">[in] The name of the key container.</span></span> <span data-ttu-id="21d74-109">`wszKeyContainer` debe ser una cadena no vacía.</span><span class="sxs-lookup"><span data-stu-id="21d74-109">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="21d74-110">[in] El par de claves binario.</span><span class="sxs-lookup"><span data-stu-id="21d74-110">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="21d74-111">[in] El tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="21d74-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21d74-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="21d74-112">Return Value</span></span>  
 <span data-ttu-id="21d74-113">`true` Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="21d74-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21d74-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21d74-114">Remarks</span></span>  
 <span data-ttu-id="21d74-115">Use la [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) función para eliminar el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="21d74-115">Use the [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) function to delete the key container.</span></span>  
  
 <span data-ttu-id="21d74-116">Si el `StrongNameKeyInstall` función no se completan correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="21d74-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21d74-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21d74-117">Requirements</span></span>  
 <span data-ttu-id="21d74-118">**Plataformas:** WindSee [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21d74-118">**Platforms:** WindSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21d74-119">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="21d74-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="21d74-120">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="21d74-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="21d74-121">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21d74-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21d74-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="21d74-122">See Also</span></span>  
 [<span data-ttu-id="21d74-123">StrongNameKeyInstall (método)</span><span class="sxs-lookup"><span data-stu-id="21d74-123">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="21d74-124">StrongNameKeyDelete (método)</span><span class="sxs-lookup"><span data-stu-id="21d74-124">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="21d74-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="21d74-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
