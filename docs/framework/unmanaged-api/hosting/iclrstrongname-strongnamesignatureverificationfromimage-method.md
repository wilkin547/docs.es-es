---
title: ICLRStrongName::StrongNameSignatureVerificationFromImage (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type:
- apiref
ms.openlocfilehash: 1bfc41fdad35a7e0560d251179ea035c96aecab7
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899532"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="f151a-102">ICLRStrongName::StrongNameSignatureVerificationFromImage (Método)</span><span class="sxs-lookup"><span data-stu-id="f151a-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>
<span data-ttu-id="f151a-103">Comprueba si un ensamblado que ya se ha asignado a la memoria es válido para la clave pública asociada.</span><span class="sxs-lookup"><span data-stu-id="f151a-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f151a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f151a-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f151a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f151a-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="f151a-106">de Dirección virtual relativa del manifiesto del ensamblado asignado.</span><span class="sxs-lookup"><span data-stu-id="f151a-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="f151a-107">de Tamaño, en bytes, de la imagen asignada.</span><span class="sxs-lookup"><span data-stu-id="f151a-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="f151a-108">de Marcas que influyen en el comportamiento de la comprobación.</span><span class="sxs-lookup"><span data-stu-id="f151a-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="f151a-109">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="f151a-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="f151a-110">`SN_INFLAG_FORCE_VER` (0x00000001): fuerza la comprobación aunque sea necesario invalidar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="f151a-110">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="f151a-111">`SN_INFLAG_INSTALL` (0x00000002): especifica que esta es la primera comprobación realizada en esta imagen.</span><span class="sxs-lookup"><span data-stu-id="f151a-111">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
- <span data-ttu-id="f151a-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004): especifica que la memoria caché permitirá el acceso solo a los usuarios que tengan privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="f151a-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="f151a-113">`SN_INFLAG_USER_ACCESS` (0x00000008): especifica que el ensamblado solo será accesible para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="f151a-113">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="f151a-114">`SN_INFLAG_ALL_ACCESS` (0x00000010): especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.</span><span class="sxs-lookup"><span data-stu-id="f151a-114">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="f151a-115">`SN_INFLAG_RUNTIME` (0x80000000): reservado para la depuración interna.</span><span class="sxs-lookup"><span data-stu-id="f151a-115">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="f151a-116">enuncia Marca para la información de salida adicional.</span><span class="sxs-lookup"><span data-stu-id="f151a-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="f151a-117">Se admite el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="f151a-117">The following value is supported:</span></span>  
  
- <span data-ttu-id="f151a-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="f151a-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f151a-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f151a-119">Return Value</span></span>  
 <span data-ttu-id="f151a-120">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="f151a-120">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f151a-121">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f151a-121">Requirements</span></span>  
 <span data-ttu-id="f151a-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f151a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f151a-123">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="f151a-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f151a-124">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f151a-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f151a-125">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f151a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f151a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f151a-126">See also</span></span>

- [<span data-ttu-id="f151a-127">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f151a-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
