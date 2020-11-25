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
ms.openlocfilehash: c97cc0c1d4c022583d0823abeff998e2ed5f719e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710979"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="fe4bb-102">StrongNameGetPublicKey (Función)</span><span class="sxs-lookup"><span data-stu-id="fe4bb-102">StrongNameGetPublicKey Function</span></span>

<span data-ttu-id="fe4bb-103">Obtiene la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="fe4bb-104">El par de claves se puede proporcionar como un nombre de contenedor de claves dentro de un proveedor de servicios criptográficos (CSP) o como una colección de bytes sin procesar.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="fe4bb-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-105">This function has been deprecated.</span></span> <span data-ttu-id="fe4bb-106">Use el método [ICLRStrongName:: StrongNameGetPublicKey (](../hosting/iclrstrongname-strongnamegetpublickey-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe4bb-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe4bb-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe4bb-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe4bb-108">Parameters</span></span>  

 `szKeyContainer`  
 <span data-ttu-id="fe4bb-109">de Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="fe4bb-110">Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido en el CSP.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="fe4bb-111">En este caso, `StrongNameGetPublicKey` extrae la clave pública del par de claves almacenado en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="fe4bb-112">Si `pbKeyBlob` no es null, se supone que el par de claves está incluido en el objeto binario grande (BLOB) de clave.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="fe4bb-113">Las claves deben ser claves de firma de Rivest-Shamir-Adleman (RSA) de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="fe4bb-114">En este momento no se admite ningún otro tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="fe4bb-115">de Puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="fe4bb-116">Este par está en el formato creado por la función de Win32 `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="fe4bb-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="fe4bb-117">Si `pbKeyBlob` es null, se supone que el contenedor de claves especificado por `szKeyContainer` contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="fe4bb-118">de Tamaño, en bytes, de `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="fe4bb-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="fe4bb-119">enuncia El BLOB de clave pública devuelto.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="fe4bb-120">El `ppbPublicKeyBlob` Common Language Runtime asigna el parámetro y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="fe4bb-121">El autor de la llamada debe liberar la memoria mediante la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="fe4bb-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="fe4bb-122">enuncia Tamaño del BLOB de clave pública devuelto.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe4bb-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fe4bb-123">Return Value</span></span>  

 <span data-ttu-id="fe4bb-124">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="fe4bb-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe4bb-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe4bb-125">Remarks</span></span>  

 <span data-ttu-id="fe4bb-126">La clave pública está contenida en una estructura [PublicKeyBlob](publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="fe4bb-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="fe4bb-127">Si la `StrongNameGetPublicKey` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="fe4bb-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe4bb-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe4bb-128">Requirements</span></span>  

 <span data-ttu-id="fe4bb-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe4bb-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe4bb-130">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="fe4bb-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="fe4bb-131">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fe4bb-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe4bb-132">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe4bb-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe4bb-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fe4bb-133">See also</span></span>

- [<span data-ttu-id="fe4bb-134">Método StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="fe4bb-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="fe4bb-135">Método StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="fe4bb-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="fe4bb-136">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe4bb-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="fe4bb-137">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="fe4bb-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
