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
ms.openlocfilehash: a08aef367f300f7617e3bc9dc721b904f6f33626
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176362"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="09f59-102">ICLRStrongName::StrongNameFreeBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="09f59-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="09f59-103">Libera la memoria asignada con una llamada anterior a un método de nombre seguro como [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)o [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span><span class="sxs-lookup"><span data-stu-id="09f59-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09f59-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09f59-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09f59-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09f59-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="09f59-106">[en] Un puntero a la memoria para liberar.</span><span class="sxs-lookup"><span data-stu-id="09f59-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09f59-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="09f59-107">Return Value</span></span>  
 <span data-ttu-id="09f59-108">`S_OK`si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (consulte [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="09f59-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09f59-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09f59-109">Requirements</span></span>  
 <span data-ttu-id="09f59-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09f59-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09f59-111">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="09f59-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="09f59-112">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="09f59-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09f59-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09f59-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09f59-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="09f59-114">See also</span></span>

- [<span data-ttu-id="09f59-115">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="09f59-115">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
