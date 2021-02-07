---
description: 'Más información acerca de: PublicKeyBlob (estructura)'
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
ms.openlocfilehash: 94c1ea3d5a41bbb8941658e87f97cd6d6336187a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736504"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="a20ba-103">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="a20ba-103">PublicKeyBlob Structure</span></span>

<span data-ttu-id="a20ba-104">Representa, en formato binario, la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="a20ba-104">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a20ba-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a20ba-105">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;
```  
  
## <a name="members"></a><span data-ttu-id="a20ba-106">Members</span><span class="sxs-lookup"><span data-stu-id="a20ba-106">Members</span></span>  
  
|<span data-ttu-id="a20ba-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="a20ba-107">Member</span></span>|<span data-ttu-id="a20ba-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a20ba-108">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="a20ba-109">Identificador del algoritmo de firma (de tipo `ALG_ID` , tal y como se define en WinCrypt. h) de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="a20ba-109">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="a20ba-110">Identificador del algoritmo hash (de tipo `ALG_ID` , tal y como se define en WinCrypt. h) de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="a20ba-110">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="a20ba-111">Longitud de la clave en bytes.</span><span class="sxs-lookup"><span data-stu-id="a20ba-111">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="a20ba-112">Matriz de bytes de longitud variable que contiene el valor de clave en el formato devuelto por la CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="a20ba-112">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a20ba-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a20ba-113">Remarks</span></span>  

 <span data-ttu-id="a20ba-114">`PublicKeyBlob` [StrongNameGetPublicKey (](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration (](strongnamesignaturegeneration-function.md)y otras funciones de nombre seguro utilizan la estructura para representar la clave pública de un par de claves pública y privada.</span><span class="sxs-lookup"><span data-stu-id="a20ba-114">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a20ba-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a20ba-115">Requirements</span></span>  

 <span data-ttu-id="a20ba-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a20ba-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a20ba-117">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="a20ba-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a20ba-118">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a20ba-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a20ba-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a20ba-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a20ba-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a20ba-120">See also</span></span>

- [<span data-ttu-id="a20ba-121">StrongNameGetPublicKey (Función)</span><span class="sxs-lookup"><span data-stu-id="a20ba-121">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="a20ba-122">StrongNameSignatureGeneration (Función)</span><span class="sxs-lookup"><span data-stu-id="a20ba-122">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
