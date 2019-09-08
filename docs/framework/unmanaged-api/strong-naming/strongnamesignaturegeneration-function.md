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
ms.openlocfilehash: 48cdd550e5d8c7c75a603d74456e99a066d5c599
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798965"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="80cbe-102">StrongNameSignatureGeneration (Función)</span><span class="sxs-lookup"><span data-stu-id="80cbe-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="80cbe-103">Genera una firma de nombres seguros para el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="80cbe-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="80cbe-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="80cbe-104">This function has been deprecated.</span></span> <span data-ttu-id="80cbe-105">Use el método [ICLRStrongName:: StrongNameSignatureGeneration (](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="80cbe-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80cbe-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80cbe-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="80cbe-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="80cbe-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="80cbe-108">de La ruta de acceso al archivo que contiene el manifiesto del ensamblado para el que se generará la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="80cbe-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="80cbe-109">de Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="80cbe-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="80cbe-110">Si `pbKeyBlob` es null, `wszKeyContainer` debe especificar un contenedor válido dentro del proveedor de servicios criptográficos (CSP).</span><span class="sxs-lookup"><span data-stu-id="80cbe-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="80cbe-111">En este caso, el par de claves almacenado en el contenedor se usa para firmar el archivo.</span><span class="sxs-lookup"><span data-stu-id="80cbe-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="80cbe-112">Si `pbKeyBlob` no es null, se supone que el par de claves está incluido en el objeto binario grande (BLOB) de clave.</span><span class="sxs-lookup"><span data-stu-id="80cbe-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="80cbe-113">Las claves deben ser claves de firma de Rivest-Shamir-Adleman (RSA) de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="80cbe-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="80cbe-114">En este momento no se admite ningún otro tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="80cbe-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="80cbe-115">de Puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="80cbe-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="80cbe-116">Este par está en el formato creado por la función `CryptExportKey` de Win32.</span><span class="sxs-lookup"><span data-stu-id="80cbe-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="80cbe-117">Si `pbKeyBlob` es null, se supone que el contenedor `wszKeyContainer` de claves especificado por contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="80cbe-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="80cbe-118">de Tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="80cbe-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="80cbe-119">enuncia Puntero a la ubicación en la que el Common Language Runtime devuelve la firma.</span><span class="sxs-lookup"><span data-stu-id="80cbe-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="80cbe-120">Si `ppbSignatureBlob` es null, el Runtime almacena la firma en el archivo especificado por `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="80cbe-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="80cbe-121">Si `ppbSignatureBlob` no es null, el Common Language Runtime asigna espacio en el que se va a devolver la firma.</span><span class="sxs-lookup"><span data-stu-id="80cbe-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="80cbe-122">El autor de la llamada debe liberar este espacio mediante la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="80cbe-122">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="80cbe-123">enuncia Tamaño, en bytes, de la firma devuelta.</span><span class="sxs-lookup"><span data-stu-id="80cbe-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80cbe-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="80cbe-124">Return Value</span></span>  
 <span data-ttu-id="80cbe-125">`true`Cuando se complete correctamente; en caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="80cbe-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80cbe-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80cbe-126">Remarks</span></span>  
 <span data-ttu-id="80cbe-127">Especifique NULL para `wszFilePath` para calcular el tamaño de la firma sin crear la firma.</span><span class="sxs-lookup"><span data-stu-id="80cbe-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="80cbe-128">La firma puede almacenarse directamente en el archivo o devolverse al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="80cbe-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="80cbe-129">Si la `StrongNameSignatureGeneration` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="80cbe-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80cbe-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80cbe-130">Requirements</span></span>  
 <span data-ttu-id="80cbe-131">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80cbe-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80cbe-132">**Encabezado**: StrongName. h</span><span class="sxs-lookup"><span data-stu-id="80cbe-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="80cbe-133">**Biblioteca** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="80cbe-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80cbe-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80cbe-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80cbe-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="80cbe-135">See also</span></span>

- [<span data-ttu-id="80cbe-136">StrongNameSignatureGeneration (método)</span><span class="sxs-lookup"><span data-stu-id="80cbe-136">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="80cbe-137">StrongNameSignatureGenerationEx (método)</span><span class="sxs-lookup"><span data-stu-id="80cbe-137">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="80cbe-138">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="80cbe-138">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
