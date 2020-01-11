---
title: ICLRStrongName::StrongNameSignatureGenerationEx (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type:
- apiref
ms.openlocfilehash: 34614fe24127787a113bab4975a50f1c8d2d875e
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899495"
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a><span data-ttu-id="0ea3f-102">ICLRStrongName::StrongNameSignatureGenerationEx (Método)</span><span class="sxs-lookup"><span data-stu-id="0ea3f-102">ICLRStrongName::StrongNameSignatureGenerationEx Method</span></span>
<span data-ttu-id="0ea3f-103">Genera una firma de nombre seguro para el ensamblado especificado, según las marcas especificadas.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ea3f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ea3f-104">Syntax</span></span>  
  
```cpp
HRESULT StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ea3f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="0ea3f-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="0ea3f-106">de La ruta de acceso al archivo que contiene el manifiesto del ensamblado para el que se generará la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="0ea3f-107">de Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="0ea3f-108">Si `pbKeyBlob` es null, `wszKeyContainer` debe especificar un contenedor válido dentro del proveedor de servicios criptográficos (CSP).</span><span class="sxs-lookup"><span data-stu-id="0ea3f-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="0ea3f-109">En este caso, el par de claves almacenado en el contenedor se usa para firmar el archivo.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="0ea3f-110">Si `pbKeyBlob` no es null, se supone que el par de claves está incluido en el objeto binario grande (BLOB) de clave.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="0ea3f-111">de Puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-111">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="0ea3f-112">Este par está en el formato creado por la función `CryptExportKey` de Win32.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-112">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="0ea3f-113">Si `pbKeyBlob` es null, se supone que el contenedor de claves especificado por `wszKeyContainer` contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-113">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="0ea3f-114">de Tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-114">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="0ea3f-115">enuncia Puntero a la ubicación en la que el Common Language Runtime devuelve la firma.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-115">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="0ea3f-116">Si `ppbSignatureBlob` es null, el Runtime almacena la firma en el archivo especificado por `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-116">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="0ea3f-117">Si `ppbSignatureBlob` no es null, el Common Language Runtime asigna espacio en el que se va a devolver la firma.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-117">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="0ea3f-118">El autor de la llamada debe liberar este espacio mediante el método [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0ea3f-118">The caller must free this space using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="0ea3f-119">enuncia Tamaño, en bytes, de la firma devuelta.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-119">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0ea3f-120">de Uno o varios de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0ea3f-120">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="0ea3f-121">`SN_SIGN_ALL_FILES` (0x00000001): vuelve a calcular todos los valores hash para los módulos vinculados.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-121">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="0ea3f-122">`SN_TEST_SIGN` (0x00000002): prueba-firma del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-122">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ea3f-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0ea3f-123">Return Value</span></span>  
 <span data-ttu-id="0ea3f-124">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="0ea3f-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ea3f-125">Notas</span><span class="sxs-lookup"><span data-stu-id="0ea3f-125">Remarks</span></span>  
 <span data-ttu-id="0ea3f-126">Especifique NULL en `wszFilePath` para calcular el tamaño de la firma sin crear la firma.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-126">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="0ea3f-127">La firma puede almacenarse directamente en el archivo o devolverse al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-127">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="0ea3f-128">Si se especifica `SN_SIGN_ALL_FILES` pero no se incluye una clave pública (tanto `pbKeyBlob` como `wszFilePath` son NULL), se vuelven a calcular los valores hash de los módulos vinculados, pero no se vuelve a firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-128">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="0ea3f-129">Si se especifica `SN_TEST_SIGN`, el encabezado de Common Language Runtime no se modifica para indicar que el ensamblado está firmado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="0ea3f-129">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ea3f-130">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="0ea3f-130">Requirements</span></span>  
 <span data-ttu-id="0ea3f-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ea3f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ea3f-132">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="0ea3f-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0ea3f-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0ea3f-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ea3f-134">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ea3f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ea3f-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ea3f-135">See also</span></span>

- [<span data-ttu-id="0ea3f-136">StrongNameSignatureGeneration (método)</span><span class="sxs-lookup"><span data-stu-id="0ea3f-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="0ea3f-137">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ea3f-137">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
