---
description: 'Más información sobre: ICLRStrongName:: Strongnamekeygen ((método)'
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
ms.openlocfilehash: c445e1f0290d907f7820c0000f602f2668f59103
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799566"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="02794-103">ICLRStrongName::StrongNameKeyGen (Método)</span><span class="sxs-lookup"><span data-stu-id="02794-103">ICLRStrongName::StrongNameKeyGen Method</span></span>

<span data-ttu-id="02794-104">Crea un par de claves pública y privada para su uso en nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="02794-104">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02794-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02794-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02794-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="02794-106">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="02794-107">de Nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="02794-107">[in] The requested key container name.</span></span> <span data-ttu-id="02794-108">`wszKeyContainer` debe ser una cadena no vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="02794-108">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="02794-109">de Valor que especifica si se debe dejar la clave registrada.</span><span class="sxs-lookup"><span data-stu-id="02794-109">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="02794-110">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="02794-110">The following values are supported:</span></span>  
  
- <span data-ttu-id="02794-111">0x00000000: se utiliza cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="02794-111">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="02794-112">0x00000001 ( `SN_LEAVE_KEY` ): especifica que la clave se debe dejar registrada.</span><span class="sxs-lookup"><span data-stu-id="02794-112">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="02794-113">enuncia Par de claves pública y privada devuelta.</span><span class="sxs-lookup"><span data-stu-id="02794-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="02794-114">enuncia Tamaño, en bytes, de `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="02794-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02794-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="02794-115">Return Value</span></span>  

 <span data-ttu-id="02794-116">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="02794-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02794-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="02794-117">Remarks</span></span>  

 <span data-ttu-id="02794-118">El método [ICLRStrongName:: strongnamekeygen (](iclrstrongname-strongnamekeygen-method.md) crea una clave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="02794-118">The [ICLRStrongName::StrongNameKeyGen](iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="02794-119">Una vez recuperada la clave, debe llamar al método [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="02794-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02794-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02794-120">Requirements</span></span>  

 <span data-ttu-id="02794-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02794-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02794-122">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="02794-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="02794-123">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="02794-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02794-124">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02794-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02794-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="02794-125">See also</span></span>

- [<span data-ttu-id="02794-126">Método StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="02794-126">StrongNameKeyGenEx Method</span></span>](iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="02794-127">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="02794-127">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
