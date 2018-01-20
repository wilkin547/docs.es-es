---
title: PublicKeyBlob (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PublicKeyBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: PublicKeyBlob
helpviewer_keywords: PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1f04c692b7549c4d7d8d431591eeb867b673d9a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="b48b4-102">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="b48b4-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="b48b4-103">Representa, en formato binario, la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="b48b4-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b48b4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b48b4-104">Syntax</span></span>  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="b48b4-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b48b4-105">Members</span></span>  
  
|<span data-ttu-id="b48b4-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b48b4-106">Member</span></span>|<span data-ttu-id="b48b4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b48b4-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="b48b4-108">El identificador para el algoritmo de firma (de tipo `ALG_ID`, tal como se define en WinCrypt.h) de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="b48b4-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="b48b4-109">El identificador para el algoritmo hash (del tipo `ALG_ID`, tal como se define en WinCrypt.h) de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="b48b4-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="b48b4-110">La longitud de la clave en bytes.</span><span class="sxs-lookup"><span data-stu-id="b48b4-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="b48b4-111">Una matriz de bytes de longitud variable que contiene el valor de clave en el formato devuelto por CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="b48b4-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b48b4-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b48b4-112">Remarks</span></span>  
 <span data-ttu-id="b48b4-113">El `PublicKeyBlob` estructura se usa por [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)y otras funciones de nombre seguro para representar la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="b48b4-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b48b4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b48b4-114">Requirements</span></span>  
 <span data-ttu-id="b48b4-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b48b4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b48b4-116">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b48b4-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b48b4-117">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b48b4-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b48b4-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b48b4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b48b4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b48b4-119">See Also</span></span>  
 [<span data-ttu-id="b48b4-120">StrongNameGetPublicKey (Función)</span><span class="sxs-lookup"><span data-stu-id="b48b4-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [<span data-ttu-id="b48b4-121">StrongNameSignatureGeneration (Función)</span><span class="sxs-lookup"><span data-stu-id="b48b4-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [<span data-ttu-id="b48b4-122">Estructuras de nombres seguros</span><span class="sxs-lookup"><span data-stu-id="b48b4-122">Strong Naming Structures</span></span>](http://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
