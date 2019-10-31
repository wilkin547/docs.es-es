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
ms.openlocfilehash: 6c58a0726e0869178838999c6b000e0ad975f145
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140608"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="9da79-102">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="9da79-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="9da79-103">Representa, en formato binario, la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="9da79-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9da79-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9da79-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="9da79-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9da79-105">Members</span></span>  
  
|<span data-ttu-id="9da79-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9da79-106">Member</span></span>|<span data-ttu-id="9da79-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9da79-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="9da79-108">Identificador del algoritmo de firma (de tipo `ALG_ID`, tal y como se define en WinCrypt. h) de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="9da79-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="9da79-109">Identificador del algoritmo hash (de tipo `ALG_ID`, tal como se define en WinCrypt. h) de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="9da79-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="9da79-110">Longitud de la clave en bytes.</span><span class="sxs-lookup"><span data-stu-id="9da79-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="9da79-111">Matriz de bytes de longitud variable que contiene el valor de clave en el formato devuelto por la CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="9da79-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9da79-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9da79-112">Remarks</span></span>  
 <span data-ttu-id="9da79-113">[StrongNameGetPublicKey (](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration (](strongnamesignaturegeneration-function.md)y otras funciones de nombre seguro utilizan la estructura `PublicKeyBlob` para representar la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="9da79-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9da79-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9da79-114">Requirements</span></span>  
 <span data-ttu-id="9da79-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9da79-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9da79-116">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="9da79-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9da79-117">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9da79-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9da79-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9da79-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9da79-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9da79-119">See also</span></span>

- [<span data-ttu-id="9da79-120">StrongNameGetPublicKey (Función)</span><span class="sxs-lookup"><span data-stu-id="9da79-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="9da79-121">StrongNameSignatureGeneration (Función)</span><span class="sxs-lookup"><span data-stu-id="9da79-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
