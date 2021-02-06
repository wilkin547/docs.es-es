---
description: 'Más información acerca de: StrongNameTokenFromPublicKey ((función)'
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
ms.openlocfilehash: f978c9b2727db4b293b9c92a8789fbf9ba749d41
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636289"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="58c0e-103">StrongNameTokenFromPublicKey (Función)</span><span class="sxs-lookup"><span data-stu-id="58c0e-103">StrongNameTokenFromPublicKey Function</span></span>

<span data-ttu-id="58c0e-104">Obtiene un token que representa una clave pública.</span><span class="sxs-lookup"><span data-stu-id="58c0e-104">Gets a token representing a public key.</span></span> <span data-ttu-id="58c0e-105">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="58c0e-105">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="58c0e-106">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="58c0e-106">This function has been deprecated.</span></span> <span data-ttu-id="58c0e-107">Use el método [ICLRStrongName:: StrongNameTokenFromPublicKey (](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="58c0e-107">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c0e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58c0e-108">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58c0e-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58c0e-109">Parameters</span></span>  

 `pbPublicKeyBlob`  
 <span data-ttu-id="58c0e-110">de Estructura de tipo [PublicKeyBlob](publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="58c0e-110">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="58c0e-111">de Tamaño, en bytes, de `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="58c0e-111">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="58c0e-112">enuncia El token de nombre seguro correspondiente a la clave pasada `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="58c0e-112">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="58c0e-113">El Common Language Runtime asigna la memoria en la que se va a devolver el token.</span><span class="sxs-lookup"><span data-stu-id="58c0e-113">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="58c0e-114">El autor de la llamada debe liberar esta memoria mediante la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="58c0e-114">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="58c0e-115">enuncia Tamaño, en bytes, del token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="58c0e-115">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58c0e-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="58c0e-116">Return Value</span></span>  

 <span data-ttu-id="58c0e-117">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="58c0e-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58c0e-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="58c0e-118">Remarks</span></span>  

 <span data-ttu-id="58c0e-119">Un token de nombre seguro es la forma abreviada de una clave pública que se usa para ahorrar espacio al almacenar información de clave en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="58c0e-119">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="58c0e-120">En concreto, se usan tokens de nombre seguro en las referencias de ensamblado para hacer referencia al ensamblado dependiente.</span><span class="sxs-lookup"><span data-stu-id="58c0e-120">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="58c0e-121">Si la `StrongNameTokenFromPublicKey` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="58c0e-121">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58c0e-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58c0e-122">Requirements</span></span>  

 <span data-ttu-id="58c0e-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58c0e-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58c0e-124">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="58c0e-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="58c0e-125">**Biblioteca:** Se incluye como un recurso en mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="58c0e-125">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="58c0e-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58c0e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c0e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="58c0e-127">See also</span></span>

- [<span data-ttu-id="58c0e-128">Método StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="58c0e-128">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="58c0e-129">Método StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="58c0e-129">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="58c0e-130">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="58c0e-130">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
