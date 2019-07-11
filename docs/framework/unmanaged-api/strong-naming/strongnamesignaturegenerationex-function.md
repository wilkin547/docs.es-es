---
title: StrongNameSignatureGenerationEx (Función)
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9d2d5786ee7db334b8b9b0817c2319a6257dc9e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751748"
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="c43a2-102">StrongNameSignatureGenerationEx (Función)</span><span class="sxs-lookup"><span data-stu-id="c43a2-102">StrongNameSignatureGenerationEx Function</span></span>
<span data-ttu-id="c43a2-103">Genera una firma de nombre seguro para el ensamblado especificado, según las marcas especificadas.</span><span class="sxs-lookup"><span data-stu-id="c43a2-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="c43a2-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="c43a2-104">This function has been deprecated.</span></span> <span data-ttu-id="c43a2-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c43a2-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c43a2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c43a2-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c43a2-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c43a2-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c43a2-108">[in] La ruta de acceso al archivo que contiene el manifiesto del ensamblado para el que se generará la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c43a2-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="c43a2-109">[in] Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="c43a2-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="c43a2-110">Si `pbKeyBlob` es null, `wszKeyContainer` debe especificar un contenedor válido en el proveedor de servicios criptográficos (CSP).</span><span class="sxs-lookup"><span data-stu-id="c43a2-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="c43a2-111">En este caso, el par de claves almacenadas en el contenedor se usa para firmar el archivo.</span><span class="sxs-lookup"><span data-stu-id="c43a2-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="c43a2-112">Si `pbKeyBlob` no es null, se supone que el par de claves que se debe incluir en la clave objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="c43a2-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="c43a2-113">[in] Un puntero a la par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="c43a2-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="c43a2-114">Este par está en el formato creado por Win32 `CryptExportKey` función.</span><span class="sxs-lookup"><span data-stu-id="c43a2-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="c43a2-115">Si `pbKeyBlob` es null, el contenedor de claves especificado por `wszKeyContainer` se supone que contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="c43a2-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="c43a2-116">[in] El tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="c43a2-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="c43a2-117">[out] Un puntero a la ubicación a la que common language runtime devuelve la firma.</span><span class="sxs-lookup"><span data-stu-id="c43a2-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="c43a2-118">Si `ppbSignatureBlob` es null, el tiempo de ejecución almacena la firma en el archivo especificado por `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="c43a2-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="c43a2-119">Si `ppbSignatureBlob` es no nulo, common language runtime asigna espacio en el que se va a devolver la firma.</span><span class="sxs-lookup"><span data-stu-id="c43a2-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="c43a2-120">El llamador debe liberar este espacio mediante el [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="c43a2-120">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="c43a2-121">[out] El tamaño, en bytes, de la firma devuelta.</span><span class="sxs-lookup"><span data-stu-id="c43a2-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c43a2-122">[in] Uno o varios de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c43a2-122">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="c43a2-123">`SN_SIGN_ALL_FILES` (0 x 00000001): volver a calcular todos los códigos hash para módulos vinculados.</span><span class="sxs-lookup"><span data-stu-id="c43a2-123">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="c43a2-124">`SN_TEST_SIGN` (0 x 00000002): el ensamblado de prueba de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="c43a2-124">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c43a2-125">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c43a2-125">Return Value</span></span>  
 <span data-ttu-id="c43a2-126">`true` Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c43a2-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c43a2-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c43a2-127">Remarks</span></span>  
 <span data-ttu-id="c43a2-128">Especifique null para `wszFilePath` para calcular el tamaño de la firma sin necesidad de crear la firma.</span><span class="sxs-lookup"><span data-stu-id="c43a2-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="c43a2-129">La firma puede se almacenan directamente en el archivo, o se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="c43a2-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="c43a2-130">Si `SN_SIGN_ALL_FILES` se especifica, pero no se incluye una clave pública (ambos `pbKeyBlob` y `wszFilePath` son null), se vuelven a calcular los valores hash de los módulos vinculados, pero no se ha vuelto a firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c43a2-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="c43a2-131">Si `SN_TEST_SIGN` se especifica, el encabezado de common language runtime no se modifica para indicar que el ensamblado está firmado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c43a2-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="c43a2-132">Si el `StrongNameSignatureGenerationEx` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="c43a2-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c43a2-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c43a2-133">Requirements</span></span>  
 <span data-ttu-id="c43a2-134">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c43a2-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c43a2-135">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="c43a2-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c43a2-136">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c43a2-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c43a2-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c43a2-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c43a2-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="c43a2-138">See also</span></span>

- [<span data-ttu-id="c43a2-139">StrongNameSignatureGenerationEx (método)</span><span class="sxs-lookup"><span data-stu-id="c43a2-139">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="c43a2-140">StrongNameSignatureGeneration (método)</span><span class="sxs-lookup"><span data-stu-id="c43a2-140">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="c43a2-141">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c43a2-141">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
