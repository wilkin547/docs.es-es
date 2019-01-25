---
title: StrongNameKeyGen (Función)
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30610311d2c48f15ebd85910557892784c0cfe85
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542501"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="0a444-102">StrongNameKeyGen (Función)</span><span class="sxs-lookup"><span data-stu-id="0a444-102">StrongNameKeyGen Function</span></span>
<span data-ttu-id="0a444-103">Crea un par de claves pública y privada para su uso en nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="0a444-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="0a444-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="0a444-104">This function has been deprecated.</span></span> <span data-ttu-id="0a444-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="0a444-105">Use the [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a444-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a444-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a444-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a444-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="0a444-108">[in] El nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="0a444-108">[in] The requested key container name.</span></span> <span data-ttu-id="0a444-109">`wszKeyContainer` debe ser una cadena no vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="0a444-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0a444-110">[in] Especifica si se debe abandonar la clave registrada.</span><span class="sxs-lookup"><span data-stu-id="0a444-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="0a444-111">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0a444-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="0a444-112">0 x 00000000: se usa cuando `wszKeyContainer` es nulo para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="0a444-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="0a444-113">0 x 00000001 (`SN_LEAVE_KEY`): Especifica que se debe registrar la clave izquierda.</span><span class="sxs-lookup"><span data-stu-id="0a444-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="0a444-114">[out] El par de claves pública y privada devuelto.</span><span class="sxs-lookup"><span data-stu-id="0a444-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="0a444-115">[out] El tamaño, en bytes, de `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="0a444-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a444-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0a444-116">Return Value</span></span>  
 <span data-ttu-id="0a444-117">`true` Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="0a444-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a444-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0a444-118">Remarks</span></span>  
 <span data-ttu-id="0a444-119">El `StrongNameKeyGen` función crea una clave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="0a444-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="0a444-120">Después de recupera la clave, debe llamar a la [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) función para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="0a444-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="0a444-121">Si el `StrongNameKeyGen` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="0a444-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a444-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a444-122">Requirements</span></span>  
 <span data-ttu-id="0a444-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a444-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a444-124">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="0a444-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0a444-125">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0a444-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a444-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a444-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a444-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a444-127">See also</span></span>
- [<span data-ttu-id="0a444-128">StrongNameKeyGen (método)</span><span class="sxs-lookup"><span data-stu-id="0a444-128">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="0a444-129">StrongNameKeyGenEx (método)</span><span class="sxs-lookup"><span data-stu-id="0a444-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="0a444-130">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a444-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
