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
ms.openlocfilehash: fcdd4a3f07b4499fd2388b5d165c409da9150466
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176934"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="72d5f-102">StrongNameGetPublicKey (Función)</span><span class="sxs-lookup"><span data-stu-id="72d5f-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="72d5f-103">Obtiene la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="72d5f-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="72d5f-104">El par de claves se puede proporcionar como un nombre de contenedor de claves dentro de un proveedor de servicios criptográficos (CSP) o como una colección sin procesar de bytes.</span><span class="sxs-lookup"><span data-stu-id="72d5f-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="72d5f-105">Esta función ha quedado en desuso.</span><span class="sxs-lookup"><span data-stu-id="72d5f-105">This function has been deprecated.</span></span> <span data-ttu-id="72d5f-106">Utilice el [método ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="72d5f-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72d5f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72d5f-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72d5f-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72d5f-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="72d5f-109">[en] El nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="72d5f-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="72d5f-110">Si `pbKeyBlob` es `szKeyContainer` null, debe especificar un contenedor válido dentro del CSP.</span><span class="sxs-lookup"><span data-stu-id="72d5f-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="72d5f-111">En este `StrongNameGetPublicKey` caso, extrae la clave pública del par de claves almacenado en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="72d5f-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="72d5f-112">Si `pbKeyBlob` no es null, se supone que el par de claves está contenido en el objeto binario grande (BLOB) clave.</span><span class="sxs-lookup"><span data-stu-id="72d5f-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="72d5f-113">Las claves deben ser claves de firma Rivest-Shamir-Adleman (RSA) de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="72d5f-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="72d5f-114">No se admiten otros tipos de claves en este momento.</span><span class="sxs-lookup"><span data-stu-id="72d5f-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="72d5f-115">[en] Un puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="72d5f-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="72d5f-116">Este par tiene el formato creado `CryptExportKey` por la función Win32.</span><span class="sxs-lookup"><span data-stu-id="72d5f-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="72d5f-117">Si `pbKeyBlob` es null, se supone `szKeyContainer` que el contenedor de claves especificado por contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="72d5f-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="72d5f-118">[en] El tamaño, en `pbKeyBlob`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="72d5f-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="72d5f-119">[fuera] La clave pública devuelta BLOB.</span><span class="sxs-lookup"><span data-stu-id="72d5f-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="72d5f-120">Common `ppbPublicKeyBlob` Language Runtime asigna el parámetro y lo devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="72d5f-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="72d5f-121">El llamador debe liberar la memoria mediante el uso de la [StrongNameFreeBuffer](strongnamefreebuffer-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="72d5f-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="72d5f-122">[fuera] El tamaño de la clave pública devuelta BLOB.</span><span class="sxs-lookup"><span data-stu-id="72d5f-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72d5f-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="72d5f-123">Return Value</span></span>  
 <span data-ttu-id="72d5f-124">`true`una finalización exitosa; de `false`lo contrario, .</span><span class="sxs-lookup"><span data-stu-id="72d5f-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72d5f-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="72d5f-125">Remarks</span></span>  
 <span data-ttu-id="72d5f-126">La clave pública se encuentra en un [PublicKeyBlob](publickeyblob-structure.md) estructura.</span><span class="sxs-lookup"><span data-stu-id="72d5f-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="72d5f-127">Si `StrongNameGetPublicKey` la función no se completa correctamente, llame a la [StrongNameErrorInfo](strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="72d5f-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72d5f-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="72d5f-128">Requirements</span></span>  
 <span data-ttu-id="72d5f-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72d5f-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72d5f-130">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="72d5f-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="72d5f-131">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="72d5f-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="72d5f-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72d5f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72d5f-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="72d5f-133">See also</span></span>

- [<span data-ttu-id="72d5f-134">Método StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="72d5f-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="72d5f-135">Método StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="72d5f-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="72d5f-136">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="72d5f-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="72d5f-137">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="72d5f-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
