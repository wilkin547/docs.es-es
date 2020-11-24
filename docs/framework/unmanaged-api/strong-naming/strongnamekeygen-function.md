---
title: StrongNameKeyGen (Función)
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
ms.openlocfilehash: 4844701784a3e6a1008a5deb2bdff3b3ba47aa7e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691414"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="2139a-102">StrongNameKeyGen (Función)</span><span class="sxs-lookup"><span data-stu-id="2139a-102">StrongNameKeyGen Function</span></span>

<span data-ttu-id="2139a-103">Crea un par de claves pública y privada para su uso en nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="2139a-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="2139a-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="2139a-104">This function has been deprecated.</span></span> <span data-ttu-id="2139a-105">Use el método [ICLRStrongName:: strongnamekeygen (](../hosting/iclrstrongname-strongnamekeygen-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="2139a-105">Use the [ICLRStrongName::StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2139a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2139a-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2139a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2139a-107">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="2139a-108">de Nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="2139a-108">[in] The requested key container name.</span></span> <span data-ttu-id="2139a-109">`wszKeyContainer` debe ser una cadena no vacía, o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="2139a-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2139a-110">de Especifica si se debe dejar registrada la clave.</span><span class="sxs-lookup"><span data-stu-id="2139a-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="2139a-111">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="2139a-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="2139a-112">0x00000000: se utiliza cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="2139a-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="2139a-113">0x00000001 ( `SN_LEAVE_KEY` ): especifica que la clave se debe dejar registrada.</span><span class="sxs-lookup"><span data-stu-id="2139a-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="2139a-114">enuncia Par de claves pública y privada devuelta.</span><span class="sxs-lookup"><span data-stu-id="2139a-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="2139a-115">enuncia Tamaño, en bytes, de `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="2139a-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2139a-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2139a-116">Return Value</span></span>  

 <span data-ttu-id="2139a-117">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="2139a-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2139a-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2139a-118">Remarks</span></span>  

 <span data-ttu-id="2139a-119">La `StrongNameKeyGen` función crea una clave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="2139a-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="2139a-120">Una vez recuperada la clave, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="2139a-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="2139a-121">Si la `StrongNameKeyGen` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="2139a-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2139a-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2139a-122">Requirements</span></span>  

 <span data-ttu-id="2139a-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2139a-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2139a-124">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="2139a-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="2139a-125">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2139a-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2139a-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2139a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2139a-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2139a-127">See also</span></span>

- [<span data-ttu-id="2139a-128">Método StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="2139a-128">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="2139a-129">Método StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="2139a-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="2139a-130">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2139a-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
