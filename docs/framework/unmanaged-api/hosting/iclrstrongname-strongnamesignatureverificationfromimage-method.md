---
description: 'Más información sobre: ICLRStrongName:: Strongnamesignatureverificationfromimage ((método)'
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
ms.openlocfilehash: 5c1c3568dd0ad506c478525503f168d8b8c2dfbc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781836"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="53d1d-103">ICLRStrongName::StrongNameSignatureVerificationFromImage (Método)</span><span class="sxs-lookup"><span data-stu-id="53d1d-103">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>

<span data-ttu-id="53d1d-104">Comprueba si un ensamblado que ya se ha asignado a la memoria es válido para la clave pública asociada.</span><span class="sxs-lookup"><span data-stu-id="53d1d-104">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53d1d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53d1d-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53d1d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53d1d-106">Parameters</span></span>  

 `pbBase`  
 <span data-ttu-id="53d1d-107">de Dirección virtual relativa del manifiesto del ensamblado asignado.</span><span class="sxs-lookup"><span data-stu-id="53d1d-107">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="53d1d-108">de Tamaño, en bytes, de la imagen asignada.</span><span class="sxs-lookup"><span data-stu-id="53d1d-108">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="53d1d-109">de Marcas que influyen en el comportamiento de la comprobación.</span><span class="sxs-lookup"><span data-stu-id="53d1d-109">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="53d1d-110">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="53d1d-110">The following values are supported:</span></span>  
  
- <span data-ttu-id="53d1d-111">`SN_INFLAG_FORCE_VER` (0x00000001): fuerza la comprobación aunque sea necesario invalidar la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="53d1d-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="53d1d-112">`SN_INFLAG_INSTALL` (0x00000002): especifica que esta es la primera comprobación realizada en esta imagen.</span><span class="sxs-lookup"><span data-stu-id="53d1d-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
- <span data-ttu-id="53d1d-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004): especifica que la memoria caché permitirá el acceso solo a los usuarios que tengan privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="53d1d-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="53d1d-114">`SN_INFLAG_USER_ACCESS` (0x00000008): especifica que el ensamblado será accesible únicamente para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="53d1d-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="53d1d-115">`SN_INFLAG_ALL_ACCESS` (0x00000010): especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.</span><span class="sxs-lookup"><span data-stu-id="53d1d-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="53d1d-116">`SN_INFLAG_RUNTIME` (0x80000000): reservado para la depuración interna.</span><span class="sxs-lookup"><span data-stu-id="53d1d-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="53d1d-117">enuncia Marca para la información de salida adicional.</span><span class="sxs-lookup"><span data-stu-id="53d1d-117">[out] A flag for additional output information.</span></span> <span data-ttu-id="53d1d-118">Se admite el siguiente valor:</span><span class="sxs-lookup"><span data-stu-id="53d1d-118">The following value is supported:</span></span>  
  
- <span data-ttu-id="53d1d-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.</span><span class="sxs-lookup"><span data-stu-id="53d1d-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53d1d-120">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="53d1d-120">Return Value</span></span>  

 <span data-ttu-id="53d1d-121">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="53d1d-121">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53d1d-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53d1d-122">Requirements</span></span>  

 <span data-ttu-id="53d1d-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53d1d-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53d1d-124">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="53d1d-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="53d1d-125">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="53d1d-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53d1d-126">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53d1d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53d1d-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53d1d-127">See also</span></span>

- [<span data-ttu-id="53d1d-128">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="53d1d-128">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
