---
title: StrongNameSignatureGeneration (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a55ff59d698a1ced689e23d9908ce6e273d8a9c1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494550"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="cc67a-102">StrongNameSignatureGeneration (Función)</span><span class="sxs-lookup"><span data-stu-id="cc67a-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="cc67a-103">Genera una firma de nombres seguros para el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="cc67a-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="cc67a-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="cc67a-104">This function has been deprecated.</span></span> <span data-ttu-id="cc67a-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="cc67a-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc67a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc67a-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc67a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cc67a-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="cc67a-108">[in] La ruta de acceso al archivo que contiene el manifiesto del ensamblado para el que se generará la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="cc67a-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="cc67a-109">[in] Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="cc67a-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="cc67a-110">Si `pbKeyBlob` es null, `wszKeyContainer` debe especificar un contenedor válido en el proveedor de servicios criptográficos (CSP).</span><span class="sxs-lookup"><span data-stu-id="cc67a-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="cc67a-111">En este caso, el par de claves almacenadas en el contenedor se usa para firmar el archivo.</span><span class="sxs-lookup"><span data-stu-id="cc67a-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="cc67a-112">Si `pbKeyBlob` no es null, se supone que el par de claves que se debe incluir en la clave objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="cc67a-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="cc67a-113">Las claves deben ser de 1024 bits Rivest-Shamir-Adleman (RSA) las claves de firma.</span><span class="sxs-lookup"><span data-stu-id="cc67a-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="cc67a-114">Se admite ningún otro tipo de claves en este momento.</span><span class="sxs-lookup"><span data-stu-id="cc67a-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="cc67a-115">[in] Un puntero a la par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="cc67a-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="cc67a-116">Este par está en el formato creado por Win32 `CryptExportKey` función.</span><span class="sxs-lookup"><span data-stu-id="cc67a-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="cc67a-117">Si `pbKeyBlob` es null, el contenedor de claves especificado por `wszKeyContainer` se supone que contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="cc67a-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="cc67a-118">[in] El tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="cc67a-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="cc67a-119">[out] Un puntero a la ubicación a la que common language runtime devuelve la firma.</span><span class="sxs-lookup"><span data-stu-id="cc67a-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="cc67a-120">Si `ppbSignatureBlob` es null, el tiempo de ejecución almacena la firma en el archivo especificado por `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="cc67a-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="cc67a-121">Si `ppbSignatureBlob` es no nulo, common language runtime asigna espacio en el que se va a devolver la firma.</span><span class="sxs-lookup"><span data-stu-id="cc67a-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="cc67a-122">El llamador debe liberar este espacio mediante el [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="cc67a-122">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="cc67a-123">[out] El tamaño, en bytes, de la firma devuelta.</span><span class="sxs-lookup"><span data-stu-id="cc67a-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc67a-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cc67a-124">Return Value</span></span>  
 <span data-ttu-id="cc67a-125">`true` Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="cc67a-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc67a-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc67a-126">Remarks</span></span>  
 <span data-ttu-id="cc67a-127">Especifique null para `wszFilePath` para calcular el tamaño de la firma sin necesidad de crear la firma.</span><span class="sxs-lookup"><span data-stu-id="cc67a-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="cc67a-128">La firma se puede almacenar directamente en el archivo o la devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="cc67a-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="cc67a-129">Si el `StrongNameSignatureGeneration` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="cc67a-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc67a-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc67a-130">Requirements</span></span>  
 <span data-ttu-id="cc67a-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc67a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc67a-132">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="cc67a-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="cc67a-133">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cc67a-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cc67a-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc67a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc67a-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc67a-135">See also</span></span>
- [<span data-ttu-id="cc67a-136">StrongNameSignatureGeneration (método)</span><span class="sxs-lookup"><span data-stu-id="cc67a-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="cc67a-137">StrongNameSignatureGenerationEx (método)</span><span class="sxs-lookup"><span data-stu-id="cc67a-137">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="cc67a-138">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cc67a-138">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
