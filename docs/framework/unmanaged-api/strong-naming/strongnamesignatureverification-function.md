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
ms.openlocfilehash: 7dd61be008ba08ca2b28ae3e7e8ff6326f8a41d9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129233"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="099c0-102">StrongNameSignatureVerification (Función)</span><span class="sxs-lookup"><span data-stu-id="099c0-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="099c0-103">Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro, que se comprueba según las marcas indicadas.</span><span class="sxs-lookup"><span data-stu-id="099c0-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="099c0-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="099c0-104">This function has been deprecated.</span></span> <span data-ttu-id="099c0-105">Use el método [ICLRStrongName:: strongnamesignatureverification (](../hosting/iclrstrongname-strongnamesignatureverification-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="099c0-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="099c0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="099c0-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="099c0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="099c0-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="099c0-108">de Ruta de acceso al archivo portable ejecutable (. dll o. exe) para que lo compruebe el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="099c0-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="099c0-109">de Marcas para modificar el comportamiento de la comprobación.</span><span class="sxs-lookup"><span data-stu-id="099c0-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="099c0-110">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="099c0-110">The following values are supported:</span></span>  
  
- <span data-ttu-id="099c0-111">`SN_INFLAG_FORCE_VER` (0x00000001): fuerza la comprobación aunque sea necesario invalidar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="099c0-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="099c0-112">`SN_INFLAG_INSTALL` (0x00000002): especifica que es la primera vez que se comprueba el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="099c0-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="099c0-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004): especifica que la memoria caché permitirá el acceso solo a los usuarios que tengan privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="099c0-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="099c0-114">`SN_INFLAG_USER_ACCESS` (0x00000008): especifica que el ensamblado solo será accesible para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="099c0-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="099c0-115">`SN_INFLAG_ALL_ACCESS` (0x00000010): especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.</span><span class="sxs-lookup"><span data-stu-id="099c0-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="099c0-116">`SN_INFLAG_RUNTIME` (0x80000000): reservado para la depuración interna.</span><span class="sxs-lookup"><span data-stu-id="099c0-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="099c0-117">enuncia Marcas que indican si se ha comprobado la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="099c0-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="099c0-118">Se admite el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="099c0-118">The following value is supported:</span></span>  
  
- <span data-ttu-id="099c0-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="099c0-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="099c0-120">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="099c0-120">Return Value</span></span>  
 <span data-ttu-id="099c0-121">`true` si la comprobación se realizó correctamente; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="099c0-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="099c0-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="099c0-122">Requirements</span></span>  
 <span data-ttu-id="099c0-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="099c0-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="099c0-124">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="099c0-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="099c0-125">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="099c0-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="099c0-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="099c0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="099c0-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="099c0-127">See also</span></span>

- [<span data-ttu-id="099c0-128">StrongNameSignatureVerification (método)</span><span class="sxs-lookup"><span data-stu-id="099c0-128">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="099c0-129">StrongNameSignatureVerificationEx (método)</span><span class="sxs-lookup"><span data-stu-id="099c0-129">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="099c0-130">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="099c0-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
