---
title: ICLRStrongName::StrongNameKeyGen (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
ms.openlocfilehash: db5c0dbe57607c7a3bf8b97cee734415aa934336
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763090"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="15204-102">ICLRStrongName::StrongNameKeyGen (Método)</span><span class="sxs-lookup"><span data-stu-id="15204-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="15204-103">Crea un par de claves pública y privada para su uso en nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="15204-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15204-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15204-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15204-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15204-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="15204-106">de Nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="15204-106">[in] The requested key container name.</span></span> <span data-ttu-id="15204-107">`wszKeyContainer`debe ser una cadena no vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="15204-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="15204-108">de Valor que especifica si se debe dejar la clave registrada.</span><span class="sxs-lookup"><span data-stu-id="15204-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="15204-109">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="15204-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="15204-110">0x00000000: se utiliza cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="15204-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="15204-111">0x00000001 ( `SN_LEAVE_KEY` ): especifica que la clave se debe dejar registrada.</span><span class="sxs-lookup"><span data-stu-id="15204-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="15204-112">enuncia Par de claves pública y privada devuelta.</span><span class="sxs-lookup"><span data-stu-id="15204-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="15204-113">enuncia Tamaño, en bytes, de `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="15204-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15204-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="15204-114">Return Value</span></span>  
 <span data-ttu-id="15204-115">`S_OK`Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="15204-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15204-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15204-116">Remarks</span></span>  
 <span data-ttu-id="15204-117">El método [ICLRStrongName:: strongnamekeygen (](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) crea una clave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="15204-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="15204-118">Una vez recuperada la clave, debe llamar al método [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="15204-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15204-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15204-119">Requirements</span></span>  
 <span data-ttu-id="15204-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15204-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15204-121">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="15204-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="15204-122">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="15204-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15204-123">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15204-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15204-124">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="15204-124">See also</span></span>

- [<span data-ttu-id="15204-125">Método StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="15204-125">StrongNameKeyGenEx Method</span></span>](iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="15204-126">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="15204-126">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
