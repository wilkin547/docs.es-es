---
title: PublicKeyBlob (Estructura)
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75ba3fd634b108c996e848f48000ffcd0600b00c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774586"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="94f66-102">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="94f66-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="94f66-103">Representa, en formato binario, la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="94f66-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94f66-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94f66-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="94f66-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="94f66-105">Members</span></span>  
  
|<span data-ttu-id="94f66-106">Member</span><span class="sxs-lookup"><span data-stu-id="94f66-106">Member</span></span>|<span data-ttu-id="94f66-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="94f66-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="94f66-108">El identificador del algoritmo de firma (de tipo `ALG_ID`, tal como se define en WinCrypt.h) de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="94f66-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="94f66-109">El identificador del algoritmo hash (de tipo `ALG_ID`, tal como se define en WinCrypt.h) de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="94f66-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="94f66-110">La longitud de la clave en bytes.</span><span class="sxs-lookup"><span data-stu-id="94f66-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="94f66-111">Una matriz de bytes de longitud variable que contiene el valor de clave en el formato devuelto por CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="94f66-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94f66-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94f66-112">Remarks</span></span>  
 <span data-ttu-id="94f66-113">El `PublicKeyBlob` estructura la usa [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)y otras funciones de nombre seguro para representar la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="94f66-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94f66-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94f66-114">Requirements</span></span>  
 <span data-ttu-id="94f66-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94f66-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94f66-116">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="94f66-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="94f66-117">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="94f66-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="94f66-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94f66-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94f66-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="94f66-119">See also</span></span>

- [<span data-ttu-id="94f66-120">StrongNameGetPublicKey (Función)</span><span class="sxs-lookup"><span data-stu-id="94f66-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)
- [<span data-ttu-id="94f66-121">StrongNameSignatureGeneration (Función)</span><span class="sxs-lookup"><span data-stu-id="94f66-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)
