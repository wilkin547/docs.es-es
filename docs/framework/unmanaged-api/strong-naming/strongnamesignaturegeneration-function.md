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
ms.openlocfilehash: d7f481e5c61ec65d2e7414bd47227866f3435028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176908"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="299af-102">StrongNameSignatureGeneration (Función)</span><span class="sxs-lookup"><span data-stu-id="299af-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="299af-103">Genera una firma de nombres seguros para el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="299af-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="299af-104">Esta función ha quedado en desuso.</span><span class="sxs-lookup"><span data-stu-id="299af-104">This function has been deprecated.</span></span> <span data-ttu-id="299af-105">Utilice el método [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="299af-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="299af-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="299af-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="299af-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="299af-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="299af-108">[en] La ruta de acceso al archivo que contiene el manifiesto del ensamblado para el que se generará la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="299af-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="299af-109">[en] El nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="299af-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="299af-110">Si `pbKeyBlob` es `wszKeyContainer` null, debe especificar un contenedor válido dentro del proveedor de servicios criptográficos (CSP).</span><span class="sxs-lookup"><span data-stu-id="299af-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="299af-111">En este caso, el par de claves almacenado en el contenedor se utiliza para firmar el archivo.</span><span class="sxs-lookup"><span data-stu-id="299af-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="299af-112">Si `pbKeyBlob` no es null, se supone que el par de claves está contenido en el objeto binario grande (BLOB) clave.</span><span class="sxs-lookup"><span data-stu-id="299af-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="299af-113">Las claves deben ser claves de firma Rivest-Shamir-Adleman (RSA) de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="299af-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="299af-114">No se admiten otros tipos de claves en este momento.</span><span class="sxs-lookup"><span data-stu-id="299af-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="299af-115">[en] Un puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="299af-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="299af-116">Este par tiene el formato creado `CryptExportKey` por la función Win32.</span><span class="sxs-lookup"><span data-stu-id="299af-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="299af-117">Si `pbKeyBlob` es null, se supone `wszKeyContainer` que el contenedor de claves especificado por contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="299af-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="299af-118">[en] El tamaño, en `pbKeyBlob`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="299af-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="299af-119">[fuera] Puntero a la ubicación a la que Common Language Runtime devuelve la firma.</span><span class="sxs-lookup"><span data-stu-id="299af-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="299af-120">Si `ppbSignatureBlob` es null, el tiempo de ejecución `wszFilePath`almacena la firma en el archivo especificado por .</span><span class="sxs-lookup"><span data-stu-id="299af-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="299af-121">Si `ppbSignatureBlob` no es null, Common Language Runtime asigna espacio en el que devolver la firma.</span><span class="sxs-lookup"><span data-stu-id="299af-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="299af-122">El llamador debe liberar este espacio mediante la [strongNameFreeBuffer](strongnamefreebuffer-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="299af-122">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="299af-123">[fuera] El tamaño, en bytes, de la firma devuelta.</span><span class="sxs-lookup"><span data-stu-id="299af-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="299af-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="299af-124">Return Value</span></span>  
 <span data-ttu-id="299af-125">`true`una finalización exitosa; de `false`lo contrario, .</span><span class="sxs-lookup"><span data-stu-id="299af-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="299af-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="299af-126">Remarks</span></span>  
 <span data-ttu-id="299af-127">Especifique null `wszFilePath` for para calcular el tamaño de la firma sin crear la firma.</span><span class="sxs-lookup"><span data-stu-id="299af-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="299af-128">La firma se puede almacenar directamente en el archivo o devolver se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="299af-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="299af-129">Si `StrongNameSignatureGeneration` la función no se completa correctamente, llame a la [StrongNameErrorInfo](strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="299af-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="299af-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="299af-130">Requirements</span></span>  
 <span data-ttu-id="299af-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="299af-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="299af-132">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="299af-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="299af-133">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="299af-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="299af-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="299af-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="299af-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="299af-135">See also</span></span>

- [<span data-ttu-id="299af-136">Método StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="299af-136">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="299af-137">Método StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="299af-137">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="299af-138">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="299af-138">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
