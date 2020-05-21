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
ms.openlocfilehash: fb18b7b5ac73a1f270af6fae95a23e04b17ca5f1
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763077"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="35f79-102">ICLRStrongName::StrongNameKeyGenEx (Método)</span><span class="sxs-lookup"><span data-stu-id="35f79-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="35f79-103">Genera un nuevo par de claves pública y privada con el tamaño de clave especificado para el uso de nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="35f79-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35f79-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35f79-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35f79-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35f79-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="35f79-106">de Nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="35f79-106">[in] The requested key container name.</span></span> <span data-ttu-id="35f79-107">`wszKeyContainer`debe ser una cadena no vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="35f79-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="35f79-108">de Valor que especifica si se debe dejar la clave registrada.</span><span class="sxs-lookup"><span data-stu-id="35f79-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="35f79-109">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="35f79-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="35f79-110">0x00000000: se utiliza cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="35f79-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="35f79-111">0x00000001 ( `SN_LEAVE_KEY` ): especifica que la clave se debe dejar registrada.</span><span class="sxs-lookup"><span data-stu-id="35f79-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="35f79-112">de Tamaño solicitado de la clave, en bits.</span><span class="sxs-lookup"><span data-stu-id="35f79-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="35f79-113">enuncia Par de claves pública y privada devuelta.</span><span class="sxs-lookup"><span data-stu-id="35f79-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="35f79-114">enuncia Tamaño, en bytes, de `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="35f79-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35f79-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="35f79-115">Return Value</span></span>  
 <span data-ttu-id="35f79-116">`S_OK`Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="35f79-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35f79-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="35f79-117">Remarks</span></span>  
 <span data-ttu-id="35f79-118">Las versiones .NET Framework 1,0 y 1,1 requieren un `dwKeySize` de 1024 bits para firmar un ensamblado con un nombre seguro; la versión 2,0 agrega admite claves de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="35f79-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="35f79-119">Una vez recuperada la clave, debe llamar al método [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="35f79-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35f79-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35f79-120">Requirements</span></span>  
 <span data-ttu-id="35f79-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35f79-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35f79-122">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="35f79-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="35f79-123">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="35f79-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35f79-124">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35f79-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35f79-125">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="35f79-125">See also</span></span>

- [<span data-ttu-id="35f79-126">Método StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="35f79-126">StrongNameKeyGen Method</span></span>](iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="35f79-127">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="35f79-127">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
