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
ms.openlocfilehash: 79b2235e3645c89c2cd9ebcce079d5eb7efdd162
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128738"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="145ad-102">StrongNameKeyGen (Función)</span><span class="sxs-lookup"><span data-stu-id="145ad-102">StrongNameKeyGen Function</span></span>
<span data-ttu-id="145ad-103">Crea un par de claves pública y privada para su uso en nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="145ad-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="145ad-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="145ad-104">This function has been deprecated.</span></span> <span data-ttu-id="145ad-105">Use el método [ICLRStrongName:: strongnamekeygen (](../hosting/iclrstrongname-strongnamekeygen-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="145ad-105">Use the [ICLRStrongName::StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="145ad-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="145ad-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="145ad-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="145ad-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="145ad-108">de Nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="145ad-108">[in] The requested key container name.</span></span> <span data-ttu-id="145ad-109">`wszKeyContainer` debe ser una cadena no vacía o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="145ad-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="145ad-110">de Especifica si se debe dejar registrada la clave.</span><span class="sxs-lookup"><span data-stu-id="145ad-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="145ad-111">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="145ad-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="145ad-112">0x00000000: se usa cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="145ad-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="145ad-113">0x00000001 (`SN_LEAVE_KEY`): especifica que la clave se debe dejar registrada.</span><span class="sxs-lookup"><span data-stu-id="145ad-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="145ad-114">enuncia Par de claves pública y privada devuelta.</span><span class="sxs-lookup"><span data-stu-id="145ad-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="145ad-115">enuncia Tamaño, en bytes, de `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="145ad-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="145ad-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="145ad-116">Return Value</span></span>  
 <span data-ttu-id="145ad-117">`true` cuando se complete correctamente; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="145ad-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="145ad-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="145ad-118">Remarks</span></span>  
 <span data-ttu-id="145ad-119">La función `StrongNameKeyGen` crea una clave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="145ad-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="145ad-120">Una vez recuperada la clave, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="145ad-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="145ad-121">Si la función `StrongNameKeyGen` no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="145ad-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="145ad-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="145ad-122">Requirements</span></span>  
 <span data-ttu-id="145ad-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="145ad-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="145ad-124">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="145ad-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="145ad-125">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="145ad-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="145ad-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="145ad-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="145ad-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="145ad-127">See also</span></span>

- [<span data-ttu-id="145ad-128">StrongNameKeyGen (método)</span><span class="sxs-lookup"><span data-stu-id="145ad-128">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="145ad-129">StrongNameKeyGenEx (método)</span><span class="sxs-lookup"><span data-stu-id="145ad-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="145ad-130">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="145ad-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
