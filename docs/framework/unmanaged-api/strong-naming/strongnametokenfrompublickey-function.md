---
title: StrongNameTokenFromPublicKey (Función)
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b095d999f1e7e37c068c800e66f56c293422127
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490403"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="875b4-102">StrongNameTokenFromPublicKey (Función)</span><span class="sxs-lookup"><span data-stu-id="875b4-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="875b4-103">Obtiene un token que representa una clave pública.</span><span class="sxs-lookup"><span data-stu-id="875b4-103">Gets a token representing a public key.</span></span> <span data-ttu-id="875b4-104">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="875b4-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="875b4-105">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="875b4-105">This function has been deprecated.</span></span> <span data-ttu-id="875b4-106">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="875b4-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="875b4-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="875b4-107">Syntax</span></span>  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="875b4-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="875b4-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="875b4-109">[in] Una estructura de tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="875b4-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="875b4-110">[in] El tamaño, en bytes, de `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="875b4-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="875b4-111">[out] Pasa el token de nombre seguro correspondiente a la clave `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="875b4-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="875b4-112">Common language runtime asigna la memoria en el que se va a devolver el token.</span><span class="sxs-lookup"><span data-stu-id="875b4-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="875b4-113">El llamador debe liberar esta memoria utilizando la [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="875b4-113">The caller must free this memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="875b4-114">[out] El tamaño, en bytes, del token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="875b4-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="875b4-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="875b4-115">Return Value</span></span>  
 <span data-ttu-id="875b4-116">`true` Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="875b4-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="875b4-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="875b4-117">Remarks</span></span>  
 <span data-ttu-id="875b4-118">Un token de nombre seguro es la forma abreviada de una clave pública utilizada para ahorrar espacio al almacenar la información de clave en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="875b4-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="875b4-119">En concreto, los tokens de nombre seguro se usan en las referencias de ensamblado para hacer referencia al ensamblado dependiente.</span><span class="sxs-lookup"><span data-stu-id="875b4-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="875b4-120">Si el `StrongNameTokenFromPublicKey` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="875b4-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="875b4-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="875b4-121">Requirements</span></span>  
 <span data-ttu-id="875b4-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="875b4-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="875b4-123">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="875b4-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="875b4-124">**Biblioteca:** Incluye como recurso en mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="875b4-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="875b4-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="875b4-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="875b4-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="875b4-126">See also</span></span>
- [<span data-ttu-id="875b4-127">StrongNameTokenFromPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="875b4-127">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="875b4-128">StrongNameGetPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="875b4-128">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="875b4-129">PublicKeyBlob (estructura)</span><span class="sxs-lookup"><span data-stu-id="875b4-129">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
