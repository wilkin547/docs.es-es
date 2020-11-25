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
ms.openlocfilehash: 78a89c07b9a7ddbccee9716de37c96d23635f87b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708535"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="355cc-102">StrongNameSignatureGeneration (Función)</span><span class="sxs-lookup"><span data-stu-id="355cc-102">StrongNameSignatureGeneration Function</span></span>

<span data-ttu-id="355cc-103">Genera una firma de nombres seguros para el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="355cc-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="355cc-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="355cc-104">This function has been deprecated.</span></span> <span data-ttu-id="355cc-105">Use el método [ICLRStrongName:: StrongNameSignatureGeneration (](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="355cc-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="355cc-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="355cc-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="355cc-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="355cc-107">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="355cc-108">de La ruta de acceso al archivo que contiene el manifiesto del ensamblado para el que se generará la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="355cc-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="355cc-109">de Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="355cc-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="355cc-110">Si `pbKeyBlob` es null, `wszKeyContainer` debe especificar un contenedor válido dentro del proveedor de servicios criptográficos (CSP).</span><span class="sxs-lookup"><span data-stu-id="355cc-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="355cc-111">En este caso, el par de claves almacenado en el contenedor se usa para firmar el archivo.</span><span class="sxs-lookup"><span data-stu-id="355cc-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="355cc-112">Si `pbKeyBlob` no es null, se supone que el par de claves está incluido en el objeto binario grande (BLOB) de clave.</span><span class="sxs-lookup"><span data-stu-id="355cc-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="355cc-113">Las claves deben ser claves de firma de Rivest-Shamir-Adleman (RSA) de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="355cc-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="355cc-114">En este momento no se admite ningún otro tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="355cc-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="355cc-115">de Puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="355cc-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="355cc-116">Este par está en el formato creado por la función de Win32 `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="355cc-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="355cc-117">Si `pbKeyBlob` es null, se supone que el contenedor de claves especificado por `wszKeyContainer` contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="355cc-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="355cc-118">de Tamaño, en bytes, de `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="355cc-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="355cc-119">enuncia Puntero a la ubicación en la que el Common Language Runtime devuelve la firma.</span><span class="sxs-lookup"><span data-stu-id="355cc-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="355cc-120">Si `ppbSignatureBlob` es null, el Runtime almacena la firma en el archivo especificado por `wszFilePath` .</span><span class="sxs-lookup"><span data-stu-id="355cc-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="355cc-121">Si `ppbSignatureBlob` no es null, el Common Language Runtime asigna espacio en el que se va a devolver la firma.</span><span class="sxs-lookup"><span data-stu-id="355cc-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="355cc-122">El autor de la llamada debe liberar este espacio mediante la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="355cc-122">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="355cc-123">enuncia Tamaño, en bytes, de la firma devuelta.</span><span class="sxs-lookup"><span data-stu-id="355cc-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="355cc-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="355cc-124">Return Value</span></span>  

 <span data-ttu-id="355cc-125">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="355cc-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="355cc-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="355cc-126">Remarks</span></span>  

 <span data-ttu-id="355cc-127">Especifique NULL para `wszFilePath` para calcular el tamaño de la firma sin crear la firma.</span><span class="sxs-lookup"><span data-stu-id="355cc-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="355cc-128">La firma puede almacenarse directamente en el archivo o devolverse al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="355cc-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="355cc-129">Si la `StrongNameSignatureGeneration` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="355cc-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="355cc-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="355cc-130">Requirements</span></span>  

 <span data-ttu-id="355cc-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="355cc-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="355cc-132">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="355cc-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="355cc-133">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="355cc-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="355cc-134">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="355cc-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="355cc-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="355cc-135">See also</span></span>

- [<span data-ttu-id="355cc-136">Método StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="355cc-136">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="355cc-137">Método StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="355cc-137">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="355cc-138">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="355cc-138">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
