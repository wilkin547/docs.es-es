---
description: 'Más información sobre: ICLRStrongName:: StrongNameKeyGenEx ((método)'
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
ms.openlocfilehash: 3ea2bef5cc6a45066d010fc925f8866e8129faaa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799569"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="cf482-103">ICLRStrongName::StrongNameKeyGenEx (Método)</span><span class="sxs-lookup"><span data-stu-id="cf482-103">ICLRStrongName::StrongNameKeyGenEx Method</span></span>

<span data-ttu-id="cf482-104">Genera un nuevo par de claves pública y privada con el tamaño de clave especificado para el uso de nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="cf482-104">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf482-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf482-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf482-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf482-106">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="cf482-107">de Nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="cf482-107">[in] The requested key container name.</span></span> <span data-ttu-id="cf482-108">`wszKeyContainer` debe ser una cadena no vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="cf482-108">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="cf482-109">de Valor que especifica si se debe dejar la clave registrada.</span><span class="sxs-lookup"><span data-stu-id="cf482-109">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="cf482-110">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="cf482-110">The following values are supported:</span></span>  
  
- <span data-ttu-id="cf482-111">0x00000000: se utiliza cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="cf482-111">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="cf482-112">0x00000001 ( `SN_LEAVE_KEY` ): especifica que la clave se debe dejar registrada.</span><span class="sxs-lookup"><span data-stu-id="cf482-112">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="cf482-113">de Tamaño solicitado de la clave, en bits.</span><span class="sxs-lookup"><span data-stu-id="cf482-113">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="cf482-114">enuncia Par de claves pública y privada devuelta.</span><span class="sxs-lookup"><span data-stu-id="cf482-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="cf482-115">enuncia Tamaño, en bytes, de `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="cf482-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf482-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cf482-116">Return Value</span></span>  

 <span data-ttu-id="cf482-117">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="cf482-117">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf482-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cf482-118">Remarks</span></span>  

 <span data-ttu-id="cf482-119">Las versiones .NET Framework 1,0 y 1,1 requieren un `dwKeySize` de 1024 bits para firmar un ensamblado con un nombre seguro; la versión 2,0 agrega admite claves de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="cf482-119">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="cf482-120">Una vez recuperada la clave, debe llamar al método [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="cf482-120">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf482-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf482-121">Requirements</span></span>  

 <span data-ttu-id="cf482-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf482-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf482-123">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="cf482-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cf482-124">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cf482-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf482-125">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf482-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf482-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf482-126">See also</span></span>

- [<span data-ttu-id="cf482-127">Método StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="cf482-127">StrongNameKeyGen Method</span></span>](iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="cf482-128">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf482-128">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
