---
description: 'Más información acerca de: StrongNameSignatureGenerationEx ((función)'
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
ms.openlocfilehash: e4d35cf51df6047d3a89d4146ceb8bf62e3f1b8b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798880"
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="98d64-103">StrongNameSignatureGenerationEx (Función)</span><span class="sxs-lookup"><span data-stu-id="98d64-103">StrongNameSignatureGenerationEx Function</span></span>

<span data-ttu-id="98d64-104">Genera una firma de nombre seguro para el ensamblado especificado, según las marcas especificadas.</span><span class="sxs-lookup"><span data-stu-id="98d64-104">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="98d64-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="98d64-105">This function has been deprecated.</span></span> <span data-ttu-id="98d64-106">Use el método [ICLRStrongName:: StrongNameSignatureGenerationEx (](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="98d64-106">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98d64-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98d64-107">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="98d64-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98d64-108">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="98d64-109">de La ruta de acceso al archivo que contiene el manifiesto del ensamblado para el que se generará la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="98d64-109">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="98d64-110">de Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="98d64-110">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="98d64-111">Si `pbKeyBlob` es null, `wszKeyContainer` debe especificar un contenedor válido dentro del proveedor de servicios criptográficos (CSP).</span><span class="sxs-lookup"><span data-stu-id="98d64-111">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="98d64-112">En este caso, el par de claves almacenado en el contenedor se usa para firmar el archivo.</span><span class="sxs-lookup"><span data-stu-id="98d64-112">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="98d64-113">Si `pbKeyBlob` no es null, se supone que el par de claves está incluido en el objeto binario grande (BLOB) de clave.</span><span class="sxs-lookup"><span data-stu-id="98d64-113">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="98d64-114">de Puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="98d64-114">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="98d64-115">Este par está en el formato creado por la función de Win32 `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="98d64-115">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="98d64-116">Si `pbKeyBlob` es null, se supone que el contenedor de claves especificado por `wszKeyContainer` contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="98d64-116">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="98d64-117">de Tamaño, en bytes, de `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="98d64-117">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="98d64-118">enuncia Puntero a la ubicación en la que el Common Language Runtime devuelve la firma.</span><span class="sxs-lookup"><span data-stu-id="98d64-118">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="98d64-119">Si `ppbSignatureBlob` es null, el Runtime almacena la firma en el archivo especificado por `wszFilePath` .</span><span class="sxs-lookup"><span data-stu-id="98d64-119">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="98d64-120">Si `ppbSignatureBlob` no es null, el Common Language Runtime asigna espacio en el que se va a devolver la firma.</span><span class="sxs-lookup"><span data-stu-id="98d64-120">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="98d64-121">El autor de la llamada debe liberar este espacio mediante la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="98d64-121">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="98d64-122">enuncia Tamaño, en bytes, de la firma devuelta.</span><span class="sxs-lookup"><span data-stu-id="98d64-122">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="98d64-123">de Uno o varios de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="98d64-123">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="98d64-124">`SN_SIGN_ALL_FILES` (0x00000001): vuelve a calcular todos los valores hash para los módulos vinculados.</span><span class="sxs-lookup"><span data-stu-id="98d64-124">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="98d64-125">`SN_TEST_SIGN` (0x00000002): prueba-firma del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="98d64-125">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98d64-126">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="98d64-126">Return Value</span></span>  

 <span data-ttu-id="98d64-127">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="98d64-127">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98d64-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="98d64-128">Remarks</span></span>  

 <span data-ttu-id="98d64-129">Especifique NULL para `wszFilePath` para calcular el tamaño de la firma sin crear la firma.</span><span class="sxs-lookup"><span data-stu-id="98d64-129">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="98d64-130">La firma puede almacenarse directamente en el archivo o devolverse al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="98d64-130">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="98d64-131">Si `SN_SIGN_ALL_FILES` se especifica, pero no se incluye una clave pública ( `pbKeyBlob` y `wszFilePath` son NULL), se vuelven a calcular los valores hash de los módulos vinculados, pero no se vuelve a firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="98d64-131">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="98d64-132">Si `SN_TEST_SIGN` se especifica, el encabezado Common Language Runtime no se modifica para indicar que el ensamblado está firmado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="98d64-132">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="98d64-133">Si la `StrongNameSignatureGenerationEx` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="98d64-133">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98d64-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98d64-134">Requirements</span></span>  

 <span data-ttu-id="98d64-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98d64-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98d64-136">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="98d64-136">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="98d64-137">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="98d64-137">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="98d64-138">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98d64-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98d64-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="98d64-139">See also</span></span>

- [<span data-ttu-id="98d64-140">Método StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="98d64-140">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="98d64-141">Método StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="98d64-141">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="98d64-142">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="98d64-142">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
