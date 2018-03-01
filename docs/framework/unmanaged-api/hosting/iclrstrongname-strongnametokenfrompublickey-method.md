---
title: "ICLRStrongName::StrongNameTokenFromPublicKey (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b5ee9153cec51f279e08b0ac0838456645cd7ada
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="39a92-102">ICLRStrongName::StrongNameTokenFromPublicKey (Método)</span><span class="sxs-lookup"><span data-stu-id="39a92-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="39a92-103">Obtiene un token que representa una clave pública.</span><span class="sxs-lookup"><span data-stu-id="39a92-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="39a92-104">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="39a92-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39a92-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39a92-105">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39a92-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39a92-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="39a92-107">[in] Una estructura de tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="39a92-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="39a92-108">[in] El tamaño, en bytes, de `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="39a92-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="39a92-109">[out] Pasa el token de nombre seguro correspondiente a la clave `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="39a92-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="39a92-110">Common language runtime asigna la memoria en el que se va a devolver el token.</span><span class="sxs-lookup"><span data-stu-id="39a92-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="39a92-111">El llamador debe liberar esta memoria utilizando la [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="39a92-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="39a92-112">[out] El tamaño, en bytes, del token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="39a92-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39a92-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="39a92-113">Return Value</span></span>  
 <span data-ttu-id="39a92-114">`S_OK`Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="39a92-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39a92-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39a92-115">Remarks</span></span>  
 <span data-ttu-id="39a92-116">Un token de nombre seguro es la forma abreviada de una clave pública que se utiliza para ahorrar espacio al almacenar la información de clave en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="39a92-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="39a92-117">En concreto, tokens de nombre seguro se usan en las referencias de ensamblado para hacer referencia al ensamblado dependiente.</span><span class="sxs-lookup"><span data-stu-id="39a92-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39a92-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39a92-118">Requirements</span></span>  
 <span data-ttu-id="39a92-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39a92-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39a92-120">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="39a92-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="39a92-121">**Biblioteca:** incluye como recurso en mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="39a92-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="39a92-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39a92-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a92-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="39a92-123">See Also</span></span>  
 [<span data-ttu-id="39a92-124">StrongNameGetPublicKey (método)</span><span class="sxs-lookup"><span data-stu-id="39a92-124">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [<span data-ttu-id="39a92-125">PublicKeyBlob (estructura)</span><span class="sxs-lookup"><span data-stu-id="39a92-125">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="39a92-126">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="39a92-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
