---
title: ICLRStrongName::StrongNameTokenFromAssemblyEx (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00e425b56ae555b153685b5af0ac58b6ab4c335b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525175"
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a><span data-ttu-id="d61ba-102">ICLRStrongName::StrongNameTokenFromAssemblyEx (Método)</span><span class="sxs-lookup"><span data-stu-id="d61ba-102">ICLRStrongName::StrongNameTokenFromAssemblyEx Method</span></span>
<span data-ttu-id="d61ba-103">Crea un token de nombre seguro desde el archivo de ensamblado especificado y devuelve la clave pública que representa el token.</span><span class="sxs-lookup"><span data-stu-id="d61ba-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d61ba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d61ba-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d61ba-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d61ba-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d61ba-106">[in] La ruta de acceso al archivo ejecutable portable (PE) para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d61ba-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="d61ba-107">[out] El token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="d61ba-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="d61ba-108">[out] El tamaño, en bytes, del token de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="d61ba-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="d61ba-109">[out] La clave pública devuelta.</span><span class="sxs-lookup"><span data-stu-id="d61ba-109">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="d61ba-110">[out] El tamaño, en bytes, de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="d61ba-110">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d61ba-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d61ba-111">Return Value</span></span>  
 <span data-ttu-id="d61ba-112">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="d61ba-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d61ba-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d61ba-113">Remarks</span></span>  
 <span data-ttu-id="d61ba-114">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="d61ba-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="d61ba-115">El token es un hash de 64 bits que se crea a partir de la clave pública utilizada para firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d61ba-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="d61ba-116">El token es una parte del nombre seguro del ensamblado y se puede leer desde los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d61ba-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="d61ba-117">Después de recuperar la clave y se crea el token, debe llamar a la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="d61ba-117">After the key is retrieved and the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d61ba-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d61ba-118">Requirements</span></span>  
 <span data-ttu-id="d61ba-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d61ba-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d61ba-120">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d61ba-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d61ba-121">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d61ba-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d61ba-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d61ba-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d61ba-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d61ba-123">See Also</span></span>  
 [<span data-ttu-id="d61ba-124">StrongNameTokenFromAssembly (método)</span><span class="sxs-lookup"><span data-stu-id="d61ba-124">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="d61ba-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d61ba-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
