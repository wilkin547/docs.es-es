---
description: 'Más información acerca de: Strongnametokenfromassemblyex ((función)'
title: StrongNameTokenFromAssemblyEx (Función)
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type:
- apiref
ms.openlocfilehash: 4ca08c8cfa90415723fc2632e32aa8f45c334db3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636290"
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="d8cb0-103">StrongNameTokenFromAssemblyEx (Función)</span><span class="sxs-lookup"><span data-stu-id="d8cb0-103">StrongNameTokenFromAssemblyEx Function</span></span>

<span data-ttu-id="d8cb0-104">Crea un token de nombre seguro a partir del archivo de ensamblado especificado y devuelve la clave pública que representa el token.</span><span class="sxs-lookup"><span data-stu-id="d8cb0-104">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="d8cb0-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="d8cb0-105">This function has been deprecated.</span></span> <span data-ttu-id="d8cb0-106">Use el método [ICLRStrongName:: strongnametokenfromassemblyex (](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d8cb0-106">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8cb0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8cb0-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8cb0-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8cb0-108">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="d8cb0-109">de La ruta de acceso al archivo portable ejecutable (PE) para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d8cb0-109">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="d8cb0-110">enuncia El token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="d8cb0-110">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="d8cb0-111">enuncia Tamaño, en bytes, del token de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="d8cb0-111">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="d8cb0-112">enuncia La clave pública devuelta.</span><span class="sxs-lookup"><span data-stu-id="d8cb0-112">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="d8cb0-113">enuncia Tamaño, en bytes, de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="d8cb0-113">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8cb0-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d8cb0-114">Return Value</span></span>  

 <span data-ttu-id="d8cb0-115">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="d8cb0-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8cb0-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d8cb0-116">Remarks</span></span>  

 <span data-ttu-id="d8cb0-117">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="d8cb0-117">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="d8cb0-118">El token es un hash de 64 bits que se crea a partir de la clave pública utilizada para firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d8cb0-118">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="d8cb0-119">El token es una parte del nombre seguro del ensamblado y se puede leer desde los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d8cb0-119">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="d8cb0-120">Una vez recuperada la clave y creado el token, debe llamar a la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="d8cb0-120">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="d8cb0-121">Si la `StrongNameTokenFromAssemblyEx` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="d8cb0-121">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8cb0-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8cb0-122">Requirements</span></span>  

 <span data-ttu-id="d8cb0-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8cb0-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8cb0-124">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="d8cb0-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d8cb0-125">**Biblioteca:** Se incluye como un recurso en mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d8cb0-125">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="d8cb0-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8cb0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8cb0-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8cb0-127">See also</span></span>

- [<span data-ttu-id="d8cb0-128">Método StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="d8cb0-128">StrongNameTokenFromAssemblyEx Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="d8cb0-129">Método StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="d8cb0-129">StrongNameTokenFromAssembly Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="d8cb0-130">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8cb0-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
