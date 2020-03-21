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
ms.openlocfilehash: 3b00bf8295a635871bd7263928ff21c97053cc39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176960"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="c48af-102">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="c48af-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="c48af-103">Representa, en formato binario, la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="c48af-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c48af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c48af-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;
```  
  
## <a name="members"></a><span data-ttu-id="c48af-105">Members</span><span class="sxs-lookup"><span data-stu-id="c48af-105">Members</span></span>  
  
|<span data-ttu-id="c48af-106">Member</span><span class="sxs-lookup"><span data-stu-id="c48af-106">Member</span></span>|<span data-ttu-id="c48af-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c48af-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="c48af-108">Identificador del algoritmo de firma `ALG_ID`(de tipo , tal como se define en WinCrypt.h) de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="c48af-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="c48af-109">Identificador del algoritmo hash (de tipo `ALG_ID`, tal como se define en WinCrypt.h) de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="c48af-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="c48af-110">La longitud de la clave en bytes.</span><span class="sxs-lookup"><span data-stu-id="c48af-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="c48af-111">Matriz de bytes de longitud variable que contiene el valor de clave en el formato devuelto por CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="c48af-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c48af-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c48af-112">Remarks</span></span>  
 <span data-ttu-id="c48af-113">`PublicKeyBlob` [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)y otras funciones de nombre seguro usan la estructura para representar la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="c48af-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c48af-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c48af-114">Requirements</span></span>  
 <span data-ttu-id="c48af-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c48af-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c48af-116">**Encabezado:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="c48af-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c48af-117">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c48af-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c48af-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c48af-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c48af-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c48af-119">See also</span></span>

- [<span data-ttu-id="c48af-120">StrongNameGetPublicKey (Función)</span><span class="sxs-lookup"><span data-stu-id="c48af-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="c48af-121">StrongNameSignatureGeneration (Función)</span><span class="sxs-lookup"><span data-stu-id="c48af-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
