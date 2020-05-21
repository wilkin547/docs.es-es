---
title: ICLRStrongName::StrongNameTokenFromPublicKey (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
ms.openlocfilehash: e61a652072b424d1245518c832f9b0856e0f2021
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762609"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="c786c-102">ICLRStrongName::StrongNameTokenFromPublicKey (Método)</span><span class="sxs-lookup"><span data-stu-id="c786c-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="c786c-103">Obtiene un token que representa una clave pública.</span><span class="sxs-lookup"><span data-stu-id="c786c-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="c786c-104">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="c786c-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c786c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c786c-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c786c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c786c-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="c786c-107">de Estructura de tipo [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c786c-107">[in] A structure of type [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="c786c-108">de Tamaño, en bytes, de `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="c786c-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="c786c-109">enuncia El token de nombre seguro correspondiente a la clave pasada `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="c786c-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="c786c-110">El Common Language Runtime asigna la memoria en la que se va a devolver el token.</span><span class="sxs-lookup"><span data-stu-id="c786c-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="c786c-111">El llamador debe liberar esta memoria mediante el método [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c786c-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="c786c-112">enuncia Tamaño, en bytes, del token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="c786c-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c786c-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c786c-113">Return Value</span></span>  
 <span data-ttu-id="c786c-114">`S_OK`Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="c786c-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c786c-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c786c-115">Remarks</span></span>  
 <span data-ttu-id="c786c-116">Un token de nombre seguro es la forma abreviada de una clave pública que se usa para ahorrar espacio al almacenar información de clave en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="c786c-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="c786c-117">En concreto, se usan tokens de nombre seguro en las referencias de ensamblado para hacer referencia al ensamblado dependiente.</span><span class="sxs-lookup"><span data-stu-id="c786c-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c786c-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c786c-118">Requirements</span></span>  
 <span data-ttu-id="c786c-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c786c-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c786c-120">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="c786c-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c786c-121">**Biblioteca:** Se incluye como recurso en Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c786c-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="c786c-122">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c786c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c786c-123">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="c786c-123">See also</span></span>

- [<span data-ttu-id="c786c-124">Método StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="c786c-124">StrongNameGetPublicKey Method</span></span>](iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="c786c-125">PublicKeyBlob (Estructura)</span><span class="sxs-lookup"><span data-stu-id="c786c-125">PublicKeyBlob Structure</span></span>](../strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="c786c-126">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c786c-126">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
