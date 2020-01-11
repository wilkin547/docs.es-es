---
title: ICLRStrongName::StrongNameTokenFromAssembly (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type:
- apiref
ms.openlocfilehash: 12677799136e9ca887809e58fba838cb421ea183
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901065"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="b9ff1-102">ICLRStrongName::StrongNameTokenFromAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="b9ff1-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="b9ff1-103">Crea un token de nombre seguro desde el archivo de ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="b9ff1-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9ff1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9ff1-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9ff1-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b9ff1-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="b9ff1-106">de La ruta de acceso al archivo portable ejecutable (PE) para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b9ff1-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="b9ff1-107">enuncia El token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="b9ff1-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="b9ff1-108">enuncia Tamaño, en bytes, del token de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="b9ff1-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9ff1-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b9ff1-109">Return Value</span></span>  
 <span data-ttu-id="b9ff1-110">`S_OK` si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="b9ff1-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9ff1-111">Notas</span><span class="sxs-lookup"><span data-stu-id="b9ff1-111">Remarks</span></span>  
 <span data-ttu-id="b9ff1-112">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="b9ff1-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="b9ff1-113">El token es un hash de 64 bits que se crea a partir de la clave pública utilizada para firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b9ff1-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="b9ff1-114">El token es una parte del nombre seguro del ensamblado y se puede leer desde los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b9ff1-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="b9ff1-115">Una vez creado el token, debe llamar al método [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="b9ff1-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9ff1-116">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="b9ff1-116">Requirements</span></span>  
 <span data-ttu-id="b9ff1-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9ff1-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9ff1-118">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="b9ff1-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b9ff1-119">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b9ff1-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9ff1-120">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9ff1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9ff1-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9ff1-121">See also</span></span>

- [<span data-ttu-id="b9ff1-122">StrongNameTokenFromAssemblyEx (método)</span><span class="sxs-lookup"><span data-stu-id="b9ff1-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="b9ff1-123">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9ff1-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
