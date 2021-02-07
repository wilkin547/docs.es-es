---
description: 'Más información acerca de: StrongNameGetPublicKey ((función)'
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
ms.openlocfilehash: c94ffdd20e83b03da27b2f44ebbc279cfd8b8afc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670578"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="88275-103">StrongNameGetPublicKey (Función)</span><span class="sxs-lookup"><span data-stu-id="88275-103">StrongNameGetPublicKey Function</span></span>

<span data-ttu-id="88275-104">Obtiene la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="88275-104">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="88275-105">El par de claves se puede proporcionar como un nombre de contenedor de claves dentro de un proveedor de servicios criptográficos (CSP) o como una colección de bytes sin procesar.</span><span class="sxs-lookup"><span data-stu-id="88275-105">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="88275-106">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="88275-106">This function has been deprecated.</span></span> <span data-ttu-id="88275-107">Use el método [ICLRStrongName:: StrongNameGetPublicKey (](../hosting/iclrstrongname-strongnamegetpublickey-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="88275-107">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88275-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88275-108">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88275-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="88275-109">Parameters</span></span>  

 `szKeyContainer`  
 <span data-ttu-id="88275-110">de Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="88275-110">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="88275-111">Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido en el CSP.</span><span class="sxs-lookup"><span data-stu-id="88275-111">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="88275-112">En este caso, `StrongNameGetPublicKey` extrae la clave pública del par de claves almacenado en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="88275-112">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="88275-113">Si `pbKeyBlob` no es null, se supone que el par de claves está incluido en el objeto binario grande (BLOB) de clave.</span><span class="sxs-lookup"><span data-stu-id="88275-113">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="88275-114">Las claves deben ser claves de firma de Rivest-Shamir-Adleman (RSA) de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="88275-114">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="88275-115">En este momento no se admite ningún otro tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="88275-115">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="88275-116">de Puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="88275-116">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="88275-117">Este par está en el formato creado por la función de Win32 `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="88275-117">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="88275-118">Si `pbKeyBlob` es null, se supone que el contenedor de claves especificado por `szKeyContainer` contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="88275-118">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="88275-119">de Tamaño, en bytes, de `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="88275-119">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="88275-120">enuncia El BLOB de clave pública devuelto.</span><span class="sxs-lookup"><span data-stu-id="88275-120">[out] The returned public key BLOB.</span></span> <span data-ttu-id="88275-121">El `ppbPublicKeyBlob` Common Language Runtime asigna el parámetro y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="88275-121">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="88275-122">El autor de la llamada debe liberar la memoria mediante la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="88275-122">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="88275-123">enuncia Tamaño del BLOB de clave pública devuelto.</span><span class="sxs-lookup"><span data-stu-id="88275-123">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88275-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="88275-124">Return Value</span></span>  

 <span data-ttu-id="88275-125">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="88275-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88275-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="88275-126">Remarks</span></span>  

 <span data-ttu-id="88275-127">La clave pública está contenida en una estructura [PublicKeyBlob](publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="88275-127">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="88275-128">Si la `StrongNameGetPublicKey` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="88275-128">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88275-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88275-129">Requirements</span></span>  

 <span data-ttu-id="88275-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88275-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88275-131">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="88275-131">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="88275-132">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="88275-132">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="88275-133">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88275-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88275-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="88275-134">See also</span></span>

- [<span data-ttu-id="88275-135">Método StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="88275-135">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="88275-136">Método StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="88275-136">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="88275-137">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="88275-137">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="88275-138">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="88275-138">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
