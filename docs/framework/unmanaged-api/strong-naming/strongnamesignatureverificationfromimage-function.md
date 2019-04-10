---
title: StrongNameSignatureVerificationFromImage (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54b1d35d1c40289bad465978750ba738acf28c90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212445"
---
# <a name="strongnamesignatureverificationfromimage-function"></a><span data-ttu-id="b8f2e-102">StrongNameSignatureVerificationFromImage (Función)</span><span class="sxs-lookup"><span data-stu-id="b8f2e-102">StrongNameSignatureVerificationFromImage Function</span></span>
<span data-ttu-id="b8f2e-103">Comprueba si un ensamblado que ya se ha asignado a la memoria es válido para la clave pública asociada.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
 <span data-ttu-id="b8f2e-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-104">This function has been deprecated.</span></span> <span data-ttu-id="b8f2e-105">Use la [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-105">Use the [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8f2e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8f2e-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8f2e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8f2e-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="b8f2e-108">[in] La dirección virtual relativa del manifiesto del ensamblado asignado.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-108">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="b8f2e-109">[in] El tamaño, en bytes, de la imagen asignada.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-109">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="b8f2e-110">[in] Marcas que influyen en el comportamiento de la comprobación.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-110">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="b8f2e-111">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="b8f2e-111">The following values are supported:</span></span>  
  
-   `SN_INFLAG_FORCE_VER` <span data-ttu-id="b8f2e-112">(0 x 00000001) - fuerza la comprobación incluso si es necesario invalidar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-112">(0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   `SN_INFLAG_INSTALL` <span data-ttu-id="b8f2e-113">(0 x 00000002): Especifica que se trata de la primera comprobación realizada en esta imagen.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-113">(0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   `SN_INFLAG_ADMIN_ACCESS` <span data-ttu-id="b8f2e-114">(0 x 00000004): Especifica que la memoria caché permitirá el acceso únicamente a los usuarios que tienen privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-114">(0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   `SN_INFLAG_USER_ACCESS` <span data-ttu-id="b8f2e-115">(0 x 00000008): Especifica que el ensamblado será accesible solo para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-115">(0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   `SN_INFLAG_ALL_ACCESS` <span data-ttu-id="b8f2e-116">(0 x 00000010): Especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-116">(0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   `SN_INFLAG_RUNTIME` <span data-ttu-id="b8f2e-117">(0 x 80000000): reservado para la depuración interna.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-117">(0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="b8f2e-118">[out] Una marca para obtener información de salida adicional.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-118">[out] A flag for additional output information.</span></span> <span data-ttu-id="b8f2e-119">Se admite el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="b8f2e-119">The following value is supported:</span></span>  
  
-   `SN_OUTFLAG_WAS_VERIFIED` <span data-ttu-id="b8f2e-120">(0 x 00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-120">(0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8f2e-121">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b8f2e-121">Return Value</span></span>  
 `true` <span data-ttu-id="b8f2e-122">Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-122">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8f2e-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8f2e-123">Remarks</span></span>  
 <span data-ttu-id="b8f2e-124">Si el `StrongNameSignatureVerificationFromImage` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="b8f2e-124">If the `StrongNameSignatureVerificationFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8f2e-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8f2e-125">Requirements</span></span>  
 <span data-ttu-id="b8f2e-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8f2e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8f2e-127">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b8f2e-127">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b8f2e-128">**Biblioteca:** Incluye como recurso en mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b8f2e-128">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 **<span data-ttu-id="b8f2e-129">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b8f2e-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b8f2e-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8f2e-130">See also</span></span>

- [<span data-ttu-id="b8f2e-131">Método StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="b8f2e-131">StrongNameSignatureVerificationFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)
- [<span data-ttu-id="b8f2e-132">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8f2e-132">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
