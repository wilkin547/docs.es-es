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
ms.openlocfilehash: 245d9dc6147f4140e823b79c3816b9bc567ad712
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732692"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="a405a-102">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="a405a-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="a405a-103">Representa, en formato binario, la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="a405a-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a405a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a405a-104">Syntax</span></span>  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="a405a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a405a-105">Members</span></span>  
  
|<span data-ttu-id="a405a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a405a-106">Member</span></span>|<span data-ttu-id="a405a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a405a-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="a405a-108">El identificador del algoritmo de firma (de tipo `ALG_ID`, tal como se define en WinCrypt.h) de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="a405a-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="a405a-109">El identificador del algoritmo hash (de tipo `ALG_ID`, tal como se define en WinCrypt.h) de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="a405a-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="a405a-110">La longitud de la clave en bytes.</span><span class="sxs-lookup"><span data-stu-id="a405a-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="a405a-111">Una matriz de bytes de longitud variable que contiene el valor de clave en el formato devuelto por CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="a405a-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a405a-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a405a-112">Remarks</span></span>  
 <span data-ttu-id="a405a-113">El `PublicKeyBlob` estructura la usa [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)y otras funciones de nombre seguro para representar la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="a405a-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a405a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a405a-114">Requirements</span></span>  
 <span data-ttu-id="a405a-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a405a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a405a-116">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="a405a-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a405a-117">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a405a-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a405a-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a405a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a405a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a405a-119">See also</span></span>
- [<span data-ttu-id="a405a-120">StrongNameGetPublicKey (Función)</span><span class="sxs-lookup"><span data-stu-id="a405a-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)
- [<span data-ttu-id="a405a-121">StrongNameSignatureGeneration (Función)</span><span class="sxs-lookup"><span data-stu-id="a405a-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)
- [<span data-ttu-id="a405a-122">Estructuras de nombres seguros</span><span class="sxs-lookup"><span data-stu-id="a405a-122">Strong Naming Structures</span></span>](https://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
