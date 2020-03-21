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
ms.openlocfilehash: e58ac181c4e472c469076b880ff71e0c6afa30fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178053"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="67d6e-102">ICLRStrongName::StrongNameSignatureGeneration (Método)</span><span class="sxs-lookup"><span data-stu-id="67d6e-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="67d6e-103">Genera una firma de nombres seguros para el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="67d6e-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67d6e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67d6e-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="67d6e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="67d6e-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="67d6e-106">[en] La ruta de acceso al archivo que contiene el manifiesto del ensamblado para el que se generará la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="67d6e-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="67d6e-107">[en] El nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="67d6e-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="67d6e-108">Si `pbKeyBlob` es `wszKeyContainer` null, debe especificar un contenedor válido dentro del proveedor de servicios criptográficos (CSP).</span><span class="sxs-lookup"><span data-stu-id="67d6e-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="67d6e-109">En este caso, el par de claves almacenado en el contenedor se utiliza para firmar el archivo.</span><span class="sxs-lookup"><span data-stu-id="67d6e-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="67d6e-110">Si `pbKeyBlob` no es null, se supone que el par de claves está contenido en el objeto binario grande (BLOB) clave.</span><span class="sxs-lookup"><span data-stu-id="67d6e-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="67d6e-111">Las claves deben ser claves de firma Rivest-Shamir-Adleman (RSA) de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="67d6e-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="67d6e-112">No se admiten otros tipos de claves en este momento.</span><span class="sxs-lookup"><span data-stu-id="67d6e-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="67d6e-113">[en] Un puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="67d6e-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="67d6e-114">Este par tiene el formato creado `CryptExportKey` por la función Win32.</span><span class="sxs-lookup"><span data-stu-id="67d6e-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="67d6e-115">Si `pbKeyBlob` es null, se supone `wszKeyContainer` que el contenedor de claves especificado por contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="67d6e-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="67d6e-116">[en] El tamaño, en `pbKeyBlob`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="67d6e-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="67d6e-117">[fuera] Puntero a la ubicación a la que Common Language Runtime devuelve la firma.</span><span class="sxs-lookup"><span data-stu-id="67d6e-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="67d6e-118">Si `ppbSignatureBlob` es null, el tiempo de ejecución `wszFilePath`almacena la firma en el archivo especificado por .</span><span class="sxs-lookup"><span data-stu-id="67d6e-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="67d6e-119">Si `ppbSignatureBlob` no es null, Common Language Runtime asigna espacio en el que devolver la firma.</span><span class="sxs-lookup"><span data-stu-id="67d6e-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="67d6e-120">El llamador debe liberar este espacio mediante el método [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="67d6e-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="67d6e-121">[fuera] El tamaño, en bytes, de la firma devuelta.</span><span class="sxs-lookup"><span data-stu-id="67d6e-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67d6e-122">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="67d6e-122">Return Value</span></span>  
 <span data-ttu-id="67d6e-123">`S_OK`si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (consulte [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="67d6e-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67d6e-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="67d6e-124">Remarks</span></span>  
 <span data-ttu-id="67d6e-125">Especifique null `wszFilePath` for para calcular el tamaño de la firma sin crear la firma.</span><span class="sxs-lookup"><span data-stu-id="67d6e-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="67d6e-126">La firma se puede almacenar directamente en el archivo o devolver se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="67d6e-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67d6e-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67d6e-127">Requirements</span></span>  
 <span data-ttu-id="67d6e-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67d6e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67d6e-129">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="67d6e-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="67d6e-130">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67d6e-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67d6e-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67d6e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d6e-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67d6e-132">See also</span></span>

- [<span data-ttu-id="67d6e-133">Método StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="67d6e-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="67d6e-134">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="67d6e-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
