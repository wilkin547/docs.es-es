---
title: ICLRStrongName::StrongNameSignatureGeneration (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78a99132b1d4e0c61041bba3fe064c61c4722f19
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775680"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="fa3b8-102">ICLRStrongName::StrongNameSignatureGeneration (Método)</span><span class="sxs-lookup"><span data-stu-id="fa3b8-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="fa3b8-103">Genera una firma de nombres seguros para el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa3b8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa3b8-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa3b8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa3b8-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="fa3b8-106">[in] La ruta de acceso al archivo que contiene el manifiesto del ensamblado para el que se generará la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="fa3b8-107">[in] Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="fa3b8-108">Si `pbKeyBlob` es null, `wszKeyContainer` debe especificar un contenedor válido en el proveedor de servicios criptográficos (CSP).</span><span class="sxs-lookup"><span data-stu-id="fa3b8-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="fa3b8-109">En este caso, el par de claves almacenadas en el contenedor se usa para firmar el archivo.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="fa3b8-110">Si `pbKeyBlob` no es null, se supone que el par de claves que se debe incluir en la clave objeto binario grande (BLOB).</span><span class="sxs-lookup"><span data-stu-id="fa3b8-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="fa3b8-111">Las claves deben ser de 1024 bits Rivest-Shamir-Adleman (RSA) las claves de firma.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="fa3b8-112">Se admite ningún otro tipo de claves en este momento.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="fa3b8-113">[in] Un puntero a la par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="fa3b8-114">Este par está en el formato creado por Win32 `CryptExportKey` función.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="fa3b8-115">Si `pbKeyBlob` es null, el contenedor de claves especificado por `wszKeyContainer` se supone que contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="fa3b8-116">[in] El tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="fa3b8-117">[out] Un puntero a la ubicación a la que common language runtime devuelve la firma.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="fa3b8-118">Si `ppbSignatureBlob` es null, el tiempo de ejecución almacena la firma en el archivo especificado por `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="fa3b8-119">Si `ppbSignatureBlob` es no nulo, common language runtime asigna espacio en el que se va a devolver la firma.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="fa3b8-120">El llamador debe liberar este espacio mediante el uso de la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="fa3b8-121">[out] El tamaño, en bytes, de la firma devuelta.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa3b8-122">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fa3b8-122">Return Value</span></span>  
 <span data-ttu-id="fa3b8-123">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="fa3b8-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa3b8-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa3b8-124">Remarks</span></span>  
 <span data-ttu-id="fa3b8-125">Especifique null para `wszFilePath` para calcular el tamaño de la firma sin necesidad de crear la firma.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="fa3b8-126">La firma se puede almacenar directamente en el archivo o la devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="fa3b8-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa3b8-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa3b8-127">Requirements</span></span>  
 <span data-ttu-id="fa3b8-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa3b8-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa3b8-129">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fa3b8-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fa3b8-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa3b8-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa3b8-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa3b8-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa3b8-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa3b8-132">See also</span></span>

- [<span data-ttu-id="fa3b8-133">StrongNameSignatureGenerationEx (método)</span><span class="sxs-lookup"><span data-stu-id="fa3b8-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="fa3b8-134">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa3b8-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
