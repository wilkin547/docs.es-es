---
description: 'Más información sobre: ICLRStrongName:: StrongNameTokenFromAssembly ((método)'
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
ms.openlocfilehash: 520d327767f91763f8f2b3efea098c7c2790939e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781823"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="536ab-103">ICLRStrongName::StrongNameTokenFromAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="536ab-103">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>

<span data-ttu-id="536ab-104">Crea un token de nombre seguro desde el archivo de ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="536ab-104">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="536ab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="536ab-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="536ab-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="536ab-106">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="536ab-107">de La ruta de acceso al archivo portable ejecutable (PE) para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="536ab-107">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="536ab-108">enuncia El token de nombre seguro devuelto.</span><span class="sxs-lookup"><span data-stu-id="536ab-108">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="536ab-109">enuncia Tamaño, en bytes, del token de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="536ab-109">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="536ab-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="536ab-110">Return Value</span></span>  

 <span data-ttu-id="536ab-111">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="536ab-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="536ab-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="536ab-112">Remarks</span></span>  

 <span data-ttu-id="536ab-113">Un token de nombre seguro es la forma abreviada de una clave pública.</span><span class="sxs-lookup"><span data-stu-id="536ab-113">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="536ab-114">El token es un hash de 64 bits que se crea a partir de la clave pública utilizada para firmar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="536ab-114">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="536ab-115">El token es una parte del nombre seguro del ensamblado y se puede leer desde los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="536ab-115">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="536ab-116">Una vez creado el token, debe llamar al método [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) para liberar la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="536ab-116">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="536ab-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="536ab-117">Requirements</span></span>  

 <span data-ttu-id="536ab-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="536ab-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="536ab-119">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="536ab-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="536ab-120">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="536ab-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="536ab-121">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="536ab-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="536ab-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="536ab-122">See also</span></span>

- [<span data-ttu-id="536ab-123">Método StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="536ab-123">StrongNameTokenFromAssemblyEx Method</span></span>](iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="536ab-124">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="536ab-124">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
