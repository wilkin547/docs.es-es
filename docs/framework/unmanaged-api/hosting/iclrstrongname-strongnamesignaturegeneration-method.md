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
ms.openlocfilehash: ced7540afe931fb91240c770d76d205400157a51
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901102"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="93546-102">ICLRStrongName::StrongNameSignatureGeneration (Método)</span><span class="sxs-lookup"><span data-stu-id="93546-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="93546-103">Genera una firma de nombres seguros para el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="93546-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93546-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93546-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="93546-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="93546-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="93546-106">de La ruta de acceso al archivo que contiene el manifiesto del ensamblado para el que se generará la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="93546-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="93546-107">de Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="93546-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="93546-108">Si `pbKeyBlob` es null, `wszKeyContainer` debe especificar un contenedor válido dentro del proveedor de servicios criptográficos (CSP).</span><span class="sxs-lookup"><span data-stu-id="93546-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="93546-109">En este caso, el par de claves almacenado en el contenedor se usa para firmar el archivo.</span><span class="sxs-lookup"><span data-stu-id="93546-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="93546-110">Si `pbKeyBlob` no es null, se supone que el par de claves está incluido en el objeto binario grande (BLOB) de clave.</span><span class="sxs-lookup"><span data-stu-id="93546-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="93546-111">Las claves deben ser claves de firma de Rivest-Shamir-Adleman (RSA) de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="93546-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="93546-112">En este momento no se admite ningún otro tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="93546-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="93546-113">de Puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="93546-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="93546-114">Este par está en el formato creado por la función `CryptExportKey` de Win32.</span><span class="sxs-lookup"><span data-stu-id="93546-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="93546-115">Si `pbKeyBlob` es null, se supone que el contenedor de claves especificado por `wszKeyContainer` contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="93546-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="93546-116">de Tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="93546-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="93546-117">enuncia Puntero a la ubicación en la que el Common Language Runtime devuelve la firma.</span><span class="sxs-lookup"><span data-stu-id="93546-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="93546-118">Si `ppbSignatureBlob` es null, el Runtime almacena la firma en el archivo especificado por `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="93546-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="93546-119">Si `ppbSignatureBlob` no es null, el Common Language Runtime asigna espacio en el que se va a devolver la firma.</span><span class="sxs-lookup"><span data-stu-id="93546-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="93546-120">El autor de la llamada debe liberar este espacio mediante el método [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="93546-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="93546-121">enuncia Tamaño, en bytes, de la firma devuelta.</span><span class="sxs-lookup"><span data-stu-id="93546-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93546-122">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="93546-122">Return Value</span></span>  
 <span data-ttu-id="93546-123">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="93546-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93546-124">Notas</span><span class="sxs-lookup"><span data-stu-id="93546-124">Remarks</span></span>  
 <span data-ttu-id="93546-125">Especifique NULL en `wszFilePath` para calcular el tamaño de la firma sin crear la firma.</span><span class="sxs-lookup"><span data-stu-id="93546-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="93546-126">La firma puede almacenarse directamente en el archivo o devolverse al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="93546-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93546-127">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="93546-127">Requirements</span></span>  
 <span data-ttu-id="93546-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93546-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93546-129">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="93546-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="93546-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="93546-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="93546-131">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93546-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93546-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="93546-132">See also</span></span>

- [<span data-ttu-id="93546-133">StrongNameSignatureGenerationEx (método)</span><span class="sxs-lookup"><span data-stu-id="93546-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="93546-134">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="93546-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
