---
title: StrongNameKeyGenEx (Función)
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
ms.openlocfilehash: f28ee5767997240018d182b8303e4f65be81c702
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708548"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="3c9cc-102">StrongNameKeyGenEx (Función)</span><span class="sxs-lookup"><span data-stu-id="3c9cc-102">StrongNameKeyGenEx Function</span></span>

<span data-ttu-id="3c9cc-103">Genera un nuevo par de claves pública y privada con el tamaño de clave especificado para el uso de nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="3c9cc-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="3c9cc-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="3c9cc-104">This function has been deprecated.</span></span> <span data-ttu-id="3c9cc-105">Use el método [ICLRStrongName:: StrongNameKeyGenEx (](../hosting/iclrstrongname-strongnamekeygenex-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3c9cc-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c9cc-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c9cc-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c9cc-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c9cc-107">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="3c9cc-108">de Nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="3c9cc-108">[in] The requested key container name.</span></span> <span data-ttu-id="3c9cc-109">`wszKeyContainer` debe ser una cadena no vacía, o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="3c9cc-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3c9cc-110">de Especifica si se debe dejar registrada la clave.</span><span class="sxs-lookup"><span data-stu-id="3c9cc-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="3c9cc-111">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="3c9cc-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="3c9cc-112">0x00000000: se utiliza cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="3c9cc-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="3c9cc-113">0x00000001 ( `SN_LEAVE_KEY` ): especifica que la clave se debe dejar registrada.</span><span class="sxs-lookup"><span data-stu-id="3c9cc-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="3c9cc-114">de Tamaño solicitado de la clave, en bits.</span><span class="sxs-lookup"><span data-stu-id="3c9cc-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="3c9cc-115">enuncia Par de claves pública y privada devuelta.</span><span class="sxs-lookup"><span data-stu-id="3c9cc-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="3c9cc-116">enuncia Tamaño, en bytes, de `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="3c9cc-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c9cc-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3c9cc-117">Return Value</span></span>  

 <span data-ttu-id="3c9cc-118">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="3c9cc-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c9cc-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c9cc-119">Remarks</span></span>  

 <span data-ttu-id="3c9cc-120">Las versiones .NET Framework 1,0 y 1,1 requieren un `dwKeySize` de 1024 bits para firmar un ensamblado con un nombre seguro; la versión 2,0 agrega admite claves de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="3c9cc-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="3c9cc-121">Una vez recuperada la clave, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="3c9cc-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="3c9cc-122">Si la `StrongNameKeyGenEx` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="3c9cc-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c9cc-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c9cc-123">Requirements</span></span>  

 <span data-ttu-id="3c9cc-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c9cc-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c9cc-125">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="3c9cc-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="3c9cc-126">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c9cc-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c9cc-127">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c9cc-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c9cc-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c9cc-128">See also</span></span>

- [<span data-ttu-id="3c9cc-129">Método StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="3c9cc-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="3c9cc-130">Método StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="3c9cc-130">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="3c9cc-131">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c9cc-131">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
