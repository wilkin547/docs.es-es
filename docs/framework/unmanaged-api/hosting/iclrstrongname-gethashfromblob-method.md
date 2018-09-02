---
title: ICLRStrongName::GetHashFromBlob (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ca958f8472d7f7e1a44ad4ab237f582f92713c3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402743"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="af510-102">ICLRStrongName::GetHashFromBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="af510-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="af510-103">Obtiene un valor hash del ensamblado en la dirección de memoria especificada, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="af510-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af510-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af510-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af510-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af510-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="af510-106">[in] Un puntero a la dirección del bloque de memoria para un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="af510-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="af510-107">[in] La longitud, en bytes, del bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="af510-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="af510-108">[in, out] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="af510-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="af510-109">Usar cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="af510-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="af510-110">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="af510-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="af510-111">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="af510-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="af510-112">[out] El tamaño, en bytes, del devuelto `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="af510-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af510-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="af510-113">Return Value</span></span>  
 <span data-ttu-id="af510-114">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="af510-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af510-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af510-115">Requirements</span></span>  
 <span data-ttu-id="af510-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af510-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af510-117">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="af510-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="af510-118">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="af510-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af510-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af510-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af510-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="af510-120">See Also</span></span>  
 [<span data-ttu-id="af510-121">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af510-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
