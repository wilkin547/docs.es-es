---
title: "StrongNameSignatureGeneration (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureGeneration
helpviewer_keywords: StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26900b73e4c0b8b7501a59c3706966df5cf46120
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="5d817-102">StrongNameSignatureGeneration (Función)</span><span class="sxs-lookup"><span data-stu-id="5d817-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="5d817-103">Genera una firma de nombre seguro para el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="5d817-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="5d817-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="5d817-104">This function has been deprecated.</span></span> <span data-ttu-id="5d817-105">Use la [ICLRStrongName:: StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5d817-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d817-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d817-106">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="5d817-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d817-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="5d817-108">[in] La ruta de acceso al archivo que contiene el manifiesto del ensamblado para el que se generará la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="5d817-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="5d817-109">[in] El nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="5d817-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="5d817-110">Si `pbKeyBlob` es null, `wszKeyContainer` debe especificar un contenedor válido en el proveedor de servicios criptográficos (CSP).</span><span class="sxs-lookup"><span data-stu-id="5d817-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="5d817-111">En este caso, el par de claves que se almacenan en el contenedor se utiliza para firmar el archivo.</span><span class="sxs-lookup"><span data-stu-id="5d817-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="5d817-112">Si `pbKeyBlob` no es null, se supone que el par de claves para poder estar contenidos en la clave objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="5d817-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="5d817-113">Las claves deben ser de 1024 bits Rivest-Shamir-Adleman (RSA) claves de firma.</span><span class="sxs-lookup"><span data-stu-id="5d817-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="5d817-114">Ningún otro tipo de claves se admite en este momento.</span><span class="sxs-lookup"><span data-stu-id="5d817-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="5d817-115">[in] Un puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="5d817-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="5d817-116">Este par está en el formato creado por Win32 `CryptExportKey` función.</span><span class="sxs-lookup"><span data-stu-id="5d817-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="5d817-117">Si `pbKeyBlob` es null, el contenedor de claves especificado por `wszKeyContainer` se supone que contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="5d817-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="5d817-118">[in] El tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="5d817-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="5d817-119">[out] Un puntero a la ubicación a la que common language runtime devuelve la firma.</span><span class="sxs-lookup"><span data-stu-id="5d817-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="5d817-120">Si `ppbSignatureBlob` es null, el tiempo de ejecución almacena la firma en el archivo especificado por `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="5d817-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="5d817-121">Si `ppbSignatureBlob` es no es null, common language runtime asigna espacio en el que se va a devolver la firma.</span><span class="sxs-lookup"><span data-stu-id="5d817-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="5d817-122">El llamador debe liberar este espacio mediante la [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="5d817-122">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="5d817-123">[out] El tamaño, en bytes, de la firma devuelta.</span><span class="sxs-lookup"><span data-stu-id="5d817-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d817-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5d817-124">Return Value</span></span>  
 <span data-ttu-id="5d817-125">`true`Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="5d817-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d817-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d817-126">Remarks</span></span>  
 <span data-ttu-id="5d817-127">Especifique null para `wszFilePath` para calcular el tamaño de la firma sin necesidad de crear la firma.</span><span class="sxs-lookup"><span data-stu-id="5d817-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="5d817-128">La firma se pueden almacenar directamente en el archivo, o devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="5d817-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="5d817-129">Si el `StrongNameSignatureGeneration` función no se completan correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="5d817-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d817-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d817-130">Requirements</span></span>  
 <span data-ttu-id="5d817-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d817-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d817-132">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="5d817-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5d817-133">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d817-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5d817-134">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d817-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d817-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d817-135">See Also</span></span>  
 [<span data-ttu-id="5d817-136">StrongNameSignatureGeneration (método)</span><span class="sxs-lookup"><span data-stu-id="5d817-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [<span data-ttu-id="5d817-137">StrongNameSignatureGenerationEx (método)</span><span class="sxs-lookup"><span data-stu-id="5d817-137">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [<span data-ttu-id="5d817-138">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d817-138">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
