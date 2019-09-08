---
title: StrongNameGetPublicKey (Función)
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae87ebd0b8225f14ca029fac80528d47f5a866cf
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799062"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="5f03d-102">StrongNameGetPublicKey (Función)</span><span class="sxs-lookup"><span data-stu-id="5f03d-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="5f03d-103">Obtiene la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="5f03d-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="5f03d-104">El par de claves se puede proporcionar como un nombre de contenedor de claves dentro de un proveedor de servicios criptográficos (CSP) o como una colección de bytes sin procesar.</span><span class="sxs-lookup"><span data-stu-id="5f03d-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="5f03d-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="5f03d-105">This function has been deprecated.</span></span> <span data-ttu-id="5f03d-106">Use el método [ICLRStrongName:: StrongNameGetPublicKey (](../hosting/iclrstrongname-strongnamegetpublickey-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5f03d-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f03d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f03d-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f03d-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f03d-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="5f03d-109">de Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="5f03d-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="5f03d-110">Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido en el CSP.</span><span class="sxs-lookup"><span data-stu-id="5f03d-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="5f03d-111">En este caso, `StrongNameGetPublicKey` extrae la clave pública del par de claves almacenado en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="5f03d-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="5f03d-112">Si `pbKeyBlob` no es null, se supone que el par de claves está incluido en el objeto binario grande (BLOB) de clave.</span><span class="sxs-lookup"><span data-stu-id="5f03d-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="5f03d-113">Las claves deben ser claves de firma de Rivest-Shamir-Adleman (RSA) de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="5f03d-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="5f03d-114">En este momento no se admite ningún otro tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="5f03d-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="5f03d-115">de Puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="5f03d-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="5f03d-116">Este par está en el formato creado por la función `CryptExportKey` de Win32.</span><span class="sxs-lookup"><span data-stu-id="5f03d-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="5f03d-117">Si `pbKeyBlob` es null, se supone que el contenedor `szKeyContainer` de claves especificado por contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="5f03d-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="5f03d-118">de Tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="5f03d-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="5f03d-119">enuncia El BLOB de clave pública devuelto.</span><span class="sxs-lookup"><span data-stu-id="5f03d-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="5f03d-120">El `ppbPublicKeyBlob` Common Language Runtime asigna el parámetro y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5f03d-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="5f03d-121">El autor de la llamada debe liberar la memoria mediante la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="5f03d-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="5f03d-122">enuncia Tamaño del BLOB de clave pública devuelto.</span><span class="sxs-lookup"><span data-stu-id="5f03d-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f03d-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5f03d-123">Return Value</span></span>  
 <span data-ttu-id="5f03d-124">`true`Cuando se complete correctamente; en caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="5f03d-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f03d-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5f03d-125">Remarks</span></span>  
 <span data-ttu-id="5f03d-126">La clave pública está contenida en una estructura [PublicKeyBlob](publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="5f03d-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="5f03d-127">Si la `StrongNameGetPublicKey` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="5f03d-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f03d-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f03d-128">Requirements</span></span>  
 <span data-ttu-id="5f03d-129">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f03d-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f03d-130">**Encabezado**: StrongName. h</span><span class="sxs-lookup"><span data-stu-id="5f03d-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5f03d-131">**Biblioteca** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5f03d-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f03d-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f03d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f03d-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f03d-133">See also</span></span>

- [<span data-ttu-id="5f03d-134">StrongNameGetPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="5f03d-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="5f03d-135">StrongNameTokenFromPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="5f03d-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="5f03d-136">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f03d-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="5f03d-137">PublicKeyBlob (estructura)</span><span class="sxs-lookup"><span data-stu-id="5f03d-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
