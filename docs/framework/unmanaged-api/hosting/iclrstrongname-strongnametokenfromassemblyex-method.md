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
ms.openlocfilehash: e504aa067d51ec62d42f019c3a9e40538e374ea1
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762622"
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a><span data-ttu-id="ccc1d-102">ICLRStrongName::StrongNameTokenFromAssemblyEx (Método)</span><span class="sxs-lookup"><span data-stu-id="ccc1d-102">ICLRStrongName::StrongNameTokenFromAssemblyEx Method</span></span>
<span data-ttu-id="ccc1d-103">Crea un token de nombre seguro a partir del archivo de ensamblado especificado y devuelve la clave pública que representa el token.</span><span class="sxs-lookup"><span data-stu-id="ccc1d-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccc1d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccc1d-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccc1d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ccc1d-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="ccc1d-106">de La ruta de acceso al archivo portable ejecutable (PE) para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ccc1d-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="ccc1d-107">enuncia El token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="ccc1d-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="ccc1d-108">enuncia Tamaño, en bytes, del token de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="ccc1d-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="ccc1d-109">enuncia La clave pública devuelta.</span><span class="sxs-lookup"><span data-stu-id="ccc1d-109">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="ccc1d-110">enuncia Tamaño, en bytes, de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="ccc1d-110">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccc1d-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ccc1d-111">Return Value</span></span>  
 <span data-ttu-id="ccc1d-112">`S_OK`Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="ccc1d-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccc1d-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ccc1d-113">Remarks</span></span>  
 <span data-ttu-id="ccc1d-114">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="ccc1d-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="ccc1d-115">El token es un hash de 64 bits que se crea a partir de la clave pública utilizada para firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ccc1d-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="ccc1d-116">El token es una parte del nombre seguro del ensamblado y se puede leer desde los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ccc1d-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="ccc1d-117">Una vez recuperada la clave y creado el token, debe llamar al método [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="ccc1d-117">After the key is retrieved and the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccc1d-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccc1d-118">Requirements</span></span>  
 <span data-ttu-id="ccc1d-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccc1d-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccc1d-120">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="ccc1d-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ccc1d-121">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ccc1d-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccc1d-122">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccc1d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc1d-123">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="ccc1d-123">See also</span></span>

- [<span data-ttu-id="ccc1d-124">Método StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="ccc1d-124">StrongNameTokenFromAssembly Method</span></span>](iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="ccc1d-125">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccc1d-125">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
