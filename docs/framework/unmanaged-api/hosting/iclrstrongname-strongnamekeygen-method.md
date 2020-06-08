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
ms.openlocfilehash: 69ba58cc8c5235a15749281b3107481be9528f84
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503983"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="9a513-102">ICLRStrongName::StrongNameKeyGen (Método)</span><span class="sxs-lookup"><span data-stu-id="9a513-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="9a513-103">Crea un par de claves pública y privada para su uso en nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="9a513-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a513-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a513-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a513-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a513-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="9a513-106">de Nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="9a513-106">[in] The requested key container name.</span></span> <span data-ttu-id="9a513-107">`wszKeyContainer`debe ser una cadena no vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="9a513-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9a513-108">de Valor que especifica si se debe dejar la clave registrada.</span><span class="sxs-lookup"><span data-stu-id="9a513-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="9a513-109">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="9a513-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="9a513-110">0x00000000: se utiliza cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="9a513-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="9a513-111">0x00000001 ( `SN_LEAVE_KEY` ): especifica que la clave se debe dejar registrada.</span><span class="sxs-lookup"><span data-stu-id="9a513-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="9a513-112">enuncia Par de claves pública y privada devuelta.</span><span class="sxs-lookup"><span data-stu-id="9a513-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="9a513-113">enuncia Tamaño, en bytes, de `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="9a513-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a513-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9a513-114">Return Value</span></span>  
 <span data-ttu-id="9a513-115">`S_OK`Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="9a513-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a513-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a513-116">Remarks</span></span>  
 <span data-ttu-id="9a513-117">El método [ICLRStrongName:: strongnamekeygen (](iclrstrongname-strongnamekeygen-method.md) crea una clave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="9a513-117">The [ICLRStrongName::StrongNameKeyGen](iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="9a513-118">Una vez recuperada la clave, debe llamar al método [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="9a513-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a513-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a513-119">Requirements</span></span>  
 <span data-ttu-id="9a513-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a513-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a513-121">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="9a513-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9a513-122">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9a513-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a513-123">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a513-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a513-124">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="9a513-124">See also</span></span>

- [<span data-ttu-id="9a513-125">Método StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="9a513-125">StrongNameKeyGenEx Method</span></span>](iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="9a513-126">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9a513-126">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
