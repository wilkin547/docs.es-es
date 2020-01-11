---
title: ICLRStrongName::StrongNameKeyGenEx (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
ms.openlocfilehash: b09677a45c5d515aacb2cac709599140039a9dd8
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899553"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="aec08-102">ICLRStrongName::StrongNameKeyGenEx (Método)</span><span class="sxs-lookup"><span data-stu-id="aec08-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="aec08-103">Genera un nuevo par de claves pública y privada con el tamaño de clave especificado para el uso de nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="aec08-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aec08-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aec08-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aec08-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="aec08-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="aec08-106">de Nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="aec08-106">[in] The requested key container name.</span></span> <span data-ttu-id="aec08-107">`wszKeyContainer` debe ser una cadena no vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="aec08-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="aec08-108">de Valor que especifica si se debe dejar la clave registrada.</span><span class="sxs-lookup"><span data-stu-id="aec08-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="aec08-109">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="aec08-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="aec08-110">0x00000000: se usa cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="aec08-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="aec08-111">0x00000001 (`SN_LEAVE_KEY`): especifica que la clave se debe dejar registrada.</span><span class="sxs-lookup"><span data-stu-id="aec08-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="aec08-112">de Tamaño solicitado de la clave, en bits.</span><span class="sxs-lookup"><span data-stu-id="aec08-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="aec08-113">enuncia Par de claves pública y privada devuelta.</span><span class="sxs-lookup"><span data-stu-id="aec08-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="aec08-114">enuncia Tamaño, en bytes, de `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="aec08-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aec08-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aec08-115">Return Value</span></span>  
 <span data-ttu-id="aec08-116">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="aec08-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aec08-117">Notas</span><span class="sxs-lookup"><span data-stu-id="aec08-117">Remarks</span></span>  
 <span data-ttu-id="aec08-118">Las versiones .NET Framework 1,0 y 1,1 requieren un `dwKeySize` de 1024 bits para firmar un ensamblado con un nombre seguro. la versión 2,0 agrega compatibilidad con claves de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="aec08-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="aec08-119">Una vez recuperada la clave, debe llamar al método [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="aec08-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aec08-120">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="aec08-120">Requirements</span></span>  
 <span data-ttu-id="aec08-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aec08-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aec08-122">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="aec08-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="aec08-123">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="aec08-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aec08-124">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aec08-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aec08-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="aec08-125">See also</span></span>

- [<span data-ttu-id="aec08-126">StrongNameKeyGen (método)</span><span class="sxs-lookup"><span data-stu-id="aec08-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="aec08-127">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aec08-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
