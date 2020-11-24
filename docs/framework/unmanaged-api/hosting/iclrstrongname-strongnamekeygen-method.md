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
ms.openlocfilehash: 42a9fc1a05e97bbd893f0a2e77087e6524ad844f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674546"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="d6f30-102">ICLRStrongName::StrongNameKeyGen (Método)</span><span class="sxs-lookup"><span data-stu-id="d6f30-102">ICLRStrongName::StrongNameKeyGen Method</span></span>

<span data-ttu-id="d6f30-103">Crea un par de claves pública y privada para su uso en nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="d6f30-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6f30-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6f30-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6f30-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6f30-105">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="d6f30-106">de Nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="d6f30-106">[in] The requested key container name.</span></span> <span data-ttu-id="d6f30-107">`wszKeyContainer` debe ser una cadena no vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="d6f30-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d6f30-108">de Valor que especifica si se debe dejar la clave registrada.</span><span class="sxs-lookup"><span data-stu-id="d6f30-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="d6f30-109">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="d6f30-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="d6f30-110">0x00000000: se utiliza cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="d6f30-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="d6f30-111">0x00000001 ( `SN_LEAVE_KEY` ): especifica que la clave se debe dejar registrada.</span><span class="sxs-lookup"><span data-stu-id="d6f30-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="d6f30-112">enuncia Par de claves pública y privada devuelta.</span><span class="sxs-lookup"><span data-stu-id="d6f30-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="d6f30-113">enuncia Tamaño, en bytes, de `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="d6f30-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6f30-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d6f30-114">Return Value</span></span>  

 <span data-ttu-id="d6f30-115">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="d6f30-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6f30-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6f30-116">Remarks</span></span>  

 <span data-ttu-id="d6f30-117">El método [ICLRStrongName:: strongnamekeygen (](iclrstrongname-strongnamekeygen-method.md) crea una clave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="d6f30-117">The [ICLRStrongName::StrongNameKeyGen](iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="d6f30-118">Una vez recuperada la clave, debe llamar al método [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="d6f30-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6f30-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6f30-119">Requirements</span></span>  

 <span data-ttu-id="d6f30-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6f30-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6f30-121">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="d6f30-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d6f30-122">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d6f30-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d6f30-123">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6f30-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6f30-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6f30-124">See also</span></span>

- [<span data-ttu-id="d6f30-125">Método StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="d6f30-125">StrongNameKeyGenEx Method</span></span>](iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="d6f30-126">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6f30-126">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
