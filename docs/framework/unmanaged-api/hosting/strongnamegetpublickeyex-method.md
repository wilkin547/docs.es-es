---
description: 'Más información sobre: método Strongnamegetpublickeyex ('
title: StrongNameGetPublicKeyEx (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameGetPublicKeyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type:
- apiref
ms.openlocfilehash: bc9d40afc34509f852a0961823e264255125fa16
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679308"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="cb1f2-103">StrongNameGetPublicKeyEx (Método)</span><span class="sxs-lookup"><span data-stu-id="cb1f2-103">StrongNameGetPublicKeyEx Method</span></span>

<span data-ttu-id="cb1f2-104">Obtiene la clave pública de un par de claves pública y privada, y especifica un algoritmo hash y un algoritmo de firma.</span><span class="sxs-lookup"><span data-stu-id="cb1f2-104">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb1f2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb1f2-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb1f2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cb1f2-106">Parameters</span></span>  

 `pwzKeyContainer`  
 <span data-ttu-id="cb1f2-107">de Nombre del contenedor de claves que contiene el par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="cb1f2-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="cb1f2-108">Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido dentro del proveedor de servicios criptográficos (CSP).</span><span class="sxs-lookup"><span data-stu-id="cb1f2-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="cb1f2-109">En este caso, el `StrongNameGetPublicKeyEx` método extrae la clave pública del par de claves almacenado en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="cb1f2-109">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="cb1f2-110">Si `pbKeyBlob` no es null, se supone que el par de claves está incluido en el objeto binario grande (BLOB) de clave.</span><span class="sxs-lookup"><span data-stu-id="cb1f2-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="cb1f2-111">Las claves deben ser claves de firma de Rivest-Shamir-Adleman (RSA) de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="cb1f2-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="cb1f2-112">En este momento no se admite ningún otro tipo de clave.</span><span class="sxs-lookup"><span data-stu-id="cb1f2-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="cb1f2-113">de Puntero al par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="cb1f2-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="cb1f2-114">Este par está en el formato creado por la función de Win32 `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="cb1f2-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="cb1f2-115">Si `pbKeyBlob` es null, se supone que el contenedor de claves especificado por `szKeyContainer` contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="cb1f2-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="cb1f2-116">de Tamaño, en bytes, de `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="cb1f2-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="cb1f2-117">enuncia El BLOB de clave pública devuelto.</span><span class="sxs-lookup"><span data-stu-id="cb1f2-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="cb1f2-118">El `ppbPublicKeyBlob` Common Language Runtime asigna el parámetro y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="cb1f2-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="cb1f2-119">El llamador debe liberar memoria mediante el método [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cb1f2-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="cb1f2-120">enuncia Tamaño del BLOB de clave pública devuelto.</span><span class="sxs-lookup"><span data-stu-id="cb1f2-120">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="cb1f2-121">de Algoritmo hash del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cb1f2-121">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="cb1f2-122">Vea la sección Comentarios para obtener una lista de valores aceptados.</span><span class="sxs-lookup"><span data-stu-id="cb1f2-122">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="cb1f2-123">de Reservado para uso futuro; su valor predeterminado es NULL.</span><span class="sxs-lookup"><span data-stu-id="cb1f2-123">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb1f2-124">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cb1f2-124">Return Value</span></span>  

 <span data-ttu-id="cb1f2-125">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="cb1f2-125">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb1f2-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cb1f2-126">Remarks</span></span>  

 <span data-ttu-id="cb1f2-127">La clave pública está contenida en una estructura [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="cb1f2-127">The public key is contained in a [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb1f2-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cb1f2-128">Remarks</span></span>  

 <span data-ttu-id="cb1f2-129">En la tabla siguiente se muestra el conjunto de valores aceptados para el `uHashAlgId` parámetro.</span><span class="sxs-lookup"><span data-stu-id="cb1f2-129">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="cb1f2-130">Nombre</span><span class="sxs-lookup"><span data-stu-id="cb1f2-130">Name</span></span>|<span data-ttu-id="cb1f2-131">Value</span><span class="sxs-lookup"><span data-stu-id="cb1f2-131">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="cb1f2-132">None</span><span class="sxs-lookup"><span data-stu-id="cb1f2-132">None</span></span>|<span data-ttu-id="cb1f2-133">0</span><span class="sxs-lookup"><span data-stu-id="cb1f2-133">0</span></span>|  
|<span data-ttu-id="cb1f2-134">SHA-1</span><span class="sxs-lookup"><span data-stu-id="cb1f2-134">SHA-1</span></span>|<span data-ttu-id="cb1f2-135">0x8004</span><span class="sxs-lookup"><span data-stu-id="cb1f2-135">0x8004</span></span>|  
|<span data-ttu-id="cb1f2-136">SHA-256</span><span class="sxs-lookup"><span data-stu-id="cb1f2-136">SHA-256</span></span>|<span data-ttu-id="cb1f2-137">0x800c</span><span class="sxs-lookup"><span data-stu-id="cb1f2-137">0x800c</span></span>|  
|<span data-ttu-id="cb1f2-138">SHA-384</span><span class="sxs-lookup"><span data-stu-id="cb1f2-138">SHA-384</span></span>|<span data-ttu-id="cb1f2-139">0x800d</span><span class="sxs-lookup"><span data-stu-id="cb1f2-139">0x800d</span></span>|  
|<span data-ttu-id="cb1f2-140">SHA-512</span><span class="sxs-lookup"><span data-stu-id="cb1f2-140">SHA-512</span></span>|<span data-ttu-id="cb1f2-141">0x800e</span><span class="sxs-lookup"><span data-stu-id="cb1f2-141">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cb1f2-142">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb1f2-142">Requirements</span></span>  

 <span data-ttu-id="cb1f2-143">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb1f2-143">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb1f2-144">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="cb1f2-144">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cb1f2-145">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb1f2-145">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb1f2-146">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb1f2-146">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb1f2-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb1f2-147">See also</span></span>

- [<span data-ttu-id="cb1f2-148">Método StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="cb1f2-148">StrongNameTokenFromPublicKey Method</span></span>](iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="cb1f2-149">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="cb1f2-149">PublicKeyBlob Structure</span></span>](../strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="cb1f2-150">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb1f2-150">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
- [<span data-ttu-id="cb1f2-151">Método StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="cb1f2-151">StrongNameGetPublicKey Method</span></span>](iclrstrongname-strongnamegetpublickey-method.md)
