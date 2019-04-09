---
title: StrongNameSignatureVerification (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c398663b84637d2551b0d94bd59b9e0994721ba5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124772"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="a6e27-102">StrongNameSignatureVerification (Función)</span><span class="sxs-lookup"><span data-stu-id="a6e27-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="a6e27-103">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro, que se comprueba según las marcas indicadas.</span><span class="sxs-lookup"><span data-stu-id="a6e27-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="a6e27-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="a6e27-104">This function has been deprecated.</span></span> <span data-ttu-id="a6e27-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a6e27-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6e27-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6e27-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6e27-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a6e27-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="a6e27-108">[in] La ruta de acceso al archivo ejecutable portable (.dll o .exe) del ensamblado comprobar.</span><span class="sxs-lookup"><span data-stu-id="a6e27-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="a6e27-109">[in] Marcas para modificar el comportamiento de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a6e27-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="a6e27-110">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a6e27-110">The following values are supported:</span></span>  
  
-   `SN_INFLAG_FORCE_VER` <span data-ttu-id="a6e27-111">(0 x 00000001) - fuerza la comprobación incluso si es necesario invalidar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="a6e27-111">(0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   `SN_INFLAG_INSTALL` <span data-ttu-id="a6e27-112">(0 x 00000002): Especifica que se trata de la primera vez que se comprueba el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="a6e27-112">(0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   `SN_INFLAG_ADMIN_ACCESS` <span data-ttu-id="a6e27-113">(0 x 00000004): Especifica que la memoria caché permitirá el acceso únicamente a los usuarios que tienen privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="a6e27-113">(0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   `SN_INFLAG_USER_ACCESS` <span data-ttu-id="a6e27-114">(0 x 00000008): Especifica que el ensamblado será accesible solo para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="a6e27-114">(0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   `SN_INFLAG_ALL_ACCESS` <span data-ttu-id="a6e27-115">(0 x 00000010): Especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.</span><span class="sxs-lookup"><span data-stu-id="a6e27-115">(0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   `SN_INFLAG_RUNTIME` <span data-ttu-id="a6e27-116">(0 x 80000000): reservado para la depuración interna.</span><span class="sxs-lookup"><span data-stu-id="a6e27-116">(0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="a6e27-117">[out] Marcas que indican si se ha comprobado la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="a6e27-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="a6e27-118">Se admite el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="a6e27-118">The following value is supported:</span></span>  
  
-   `SN_OUTFLAG_WAS_VERIFIED` <span data-ttu-id="a6e27-119">(0 x 00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="a6e27-119">(0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6e27-120">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a6e27-120">Return Value</span></span>  
 `true` <span data-ttu-id="a6e27-121">Si la comprobación se realizó correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a6e27-121">if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6e27-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6e27-122">Requirements</span></span>  
 <span data-ttu-id="a6e27-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6e27-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6e27-124">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="a6e27-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a6e27-125">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6e27-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="a6e27-126">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a6e27-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a6e27-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6e27-127">See also</span></span>

- [<span data-ttu-id="a6e27-128">Método StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="a6e27-128">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="a6e27-129">Método StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="a6e27-129">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="a6e27-130">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6e27-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
