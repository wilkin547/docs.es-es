---
description: 'Más información acerca de: Strongnamekeygen ((función)'
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
ms.openlocfilehash: c5f4cfcfa9030ae856acf5fd59ab34a2b8338670
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636275"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="5cb9c-103">StrongNameKeyGen (Función)</span><span class="sxs-lookup"><span data-stu-id="5cb9c-103">StrongNameKeyGen Function</span></span>

<span data-ttu-id="5cb9c-104">Crea un par de claves pública y privada para su uso en nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="5cb9c-104">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="5cb9c-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="5cb9c-105">This function has been deprecated.</span></span> <span data-ttu-id="5cb9c-106">Use el método [ICLRStrongName:: strongnamekeygen (](../hosting/iclrstrongname-strongnamekeygen-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5cb9c-106">Use the [ICLRStrongName::StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cb9c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5cb9c-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cb9c-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5cb9c-108">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="5cb9c-109">de Nombre del contenedor de claves solicitado.</span><span class="sxs-lookup"><span data-stu-id="5cb9c-109">[in] The requested key container name.</span></span> <span data-ttu-id="5cb9c-110">`wszKeyContainer` debe ser una cadena no vacía, o null para generar un nombre temporal.</span><span class="sxs-lookup"><span data-stu-id="5cb9c-110">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5cb9c-111">de Especifica si se debe dejar registrada la clave.</span><span class="sxs-lookup"><span data-stu-id="5cb9c-111">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="5cb9c-112">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="5cb9c-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="5cb9c-113">0x00000000: se utiliza cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.</span><span class="sxs-lookup"><span data-stu-id="5cb9c-113">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="5cb9c-114">0x00000001 ( `SN_LEAVE_KEY` ): especifica que la clave se debe dejar registrada.</span><span class="sxs-lookup"><span data-stu-id="5cb9c-114">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="5cb9c-115">enuncia Par de claves pública y privada devuelta.</span><span class="sxs-lookup"><span data-stu-id="5cb9c-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="5cb9c-116">enuncia Tamaño, en bytes, de `ppbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="5cb9c-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5cb9c-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5cb9c-117">Return Value</span></span>  

 <span data-ttu-id="5cb9c-118">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="5cb9c-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cb9c-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5cb9c-119">Remarks</span></span>  

 <span data-ttu-id="5cb9c-120">La `StrongNameKeyGen` función crea una clave de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="5cb9c-120">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="5cb9c-121">Una vez recuperada la clave, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="5cb9c-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="5cb9c-122">Si la `StrongNameKeyGen` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="5cb9c-122">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cb9c-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5cb9c-123">Requirements</span></span>  

 <span data-ttu-id="5cb9c-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cb9c-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cb9c-125">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="5cb9c-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5cb9c-126">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5cb9c-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5cb9c-127">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cb9c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cb9c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cb9c-128">See also</span></span>

- [<span data-ttu-id="5cb9c-129">Método StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="5cb9c-129">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="5cb9c-130">Método StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="5cb9c-130">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="5cb9c-131">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5cb9c-131">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
