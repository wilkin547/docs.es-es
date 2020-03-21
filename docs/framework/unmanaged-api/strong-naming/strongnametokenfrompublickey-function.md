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
ms.openlocfilehash: 20be3114908ef78966eead05ae8ba6333a491404
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175062"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="c2b08-102">StrongNameTokenFromPublicKey (Función)</span><span class="sxs-lookup"><span data-stu-id="c2b08-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="c2b08-103">Obtiene un token que representa una clave pública.</span><span class="sxs-lookup"><span data-stu-id="c2b08-103">Gets a token representing a public key.</span></span> <span data-ttu-id="c2b08-104">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="c2b08-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="c2b08-105">Esta función ha quedado en desuso.</span><span class="sxs-lookup"><span data-stu-id="c2b08-105">This function has been deprecated.</span></span> <span data-ttu-id="c2b08-106">Utilice el método [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c2b08-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2b08-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2b08-107">Syntax</span></span>  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2b08-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c2b08-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="c2b08-109">[en] Estructura de tipo [PublicKeyBlob](publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c2b08-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="c2b08-110">[en] El tamaño, en `pbPublicKeyBlob`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="c2b08-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="c2b08-111">[fuera] El token de nombre seguro `pbPublicKeyBlob`correspondiente a la clave que se pasa en .</span><span class="sxs-lookup"><span data-stu-id="c2b08-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="c2b08-112">Common Language Runtime asigna la memoria en la que se va a devolver el token.</span><span class="sxs-lookup"><span data-stu-id="c2b08-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="c2b08-113">El llamador debe liberar esta memoria mediante el uso de la [StrongNameFreeBuffer](strongnamefreebuffer-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="c2b08-113">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="c2b08-114">[fuera] El tamaño, en bytes, del token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="c2b08-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2b08-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c2b08-115">Return Value</span></span>  
 <span data-ttu-id="c2b08-116">`true`una finalización exitosa; de `false`lo contrario, .</span><span class="sxs-lookup"><span data-stu-id="c2b08-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2b08-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c2b08-117">Remarks</span></span>  
 <span data-ttu-id="c2b08-118">Un token de nombre seguro es la forma abreviada de una clave pública que se usa para ahorrar espacio al almacenar información de clave en metadatos.</span><span class="sxs-lookup"><span data-stu-id="c2b08-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="c2b08-119">En concreto, los tokens de nombre seguro se usan en las referencias de ensamblado para hacer referencia al ensamblado dependiente.</span><span class="sxs-lookup"><span data-stu-id="c2b08-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="c2b08-120">Si `StrongNameTokenFromPublicKey` la función no se completa correctamente, llame a la [StrongNameErrorInfo](strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="c2b08-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2b08-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2b08-121">Requirements</span></span>  
 <span data-ttu-id="c2b08-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2b08-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2b08-123">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="c2b08-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c2b08-124">**Biblioteca:** Incluido como recurso en mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c2b08-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="c2b08-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2b08-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2b08-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2b08-126">See also</span></span>

- [<span data-ttu-id="c2b08-127">Método StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="c2b08-127">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="c2b08-128">Método StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="c2b08-128">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="c2b08-129">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="c2b08-129">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
