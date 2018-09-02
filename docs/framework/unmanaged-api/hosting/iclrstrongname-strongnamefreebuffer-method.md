---
title: ICLRStrongName::StrongNameFreeBuffer (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameFreeBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameFreeBuffer method [.NET Framework hosting]
ms.assetid: 6148c508-bd1d-4a37-85c3-06ecb09cc857
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef8c1e96c12b554a89d012633d1e5c347dab6de4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398529"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="73632-102">ICLRStrongName::StrongNameFreeBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="73632-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="73632-103">Libera la memoria que se asignó con una llamada anterior a un método de nombre seguro como [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), o [ ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span><span class="sxs-lookup"><span data-stu-id="73632-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73632-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73632-104">Syntax</span></span>  
  
```  
HRESULT StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73632-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="73632-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="73632-106">[in] Un puntero a la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="73632-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73632-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="73632-107">Return Value</span></span>  
 <span data-ttu-id="73632-108">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="73632-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73632-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73632-109">Requirements</span></span>  
 <span data-ttu-id="73632-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73632-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73632-111">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="73632-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="73632-112">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73632-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73632-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73632-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73632-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="73632-114">See Also</span></span>  
 [<span data-ttu-id="73632-115">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="73632-115">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
