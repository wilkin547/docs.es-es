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
ms.openlocfilehash: 7aed3e6877bfcd83754d462cdba81ccc229d002f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504009"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="5b24c-102">ICLRStrongName::StrongNameFreeBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="5b24c-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="5b24c-103">Libera la memoria asignada con una llamada anterior a un método de nombre seguro como [ICLRStrongName:: StrongNameGetPublicKey (](iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName:: StrongNameTokenFromPublicKey (](iclrstrongname-strongnametokenfrompublickey-method.md)o [ICLRStrongName:: StrongNameSignatureGeneration (](iclrstrongname-strongnamesignaturegeneration-method.md).</span><span class="sxs-lookup"><span data-stu-id="5b24c-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b24c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b24c-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b24c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5b24c-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="5b24c-106">de Puntero a la memoria que se va a liberar.</span><span class="sxs-lookup"><span data-stu-id="5b24c-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b24c-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5b24c-107">Return Value</span></span>  
 <span data-ttu-id="5b24c-108">`S_OK`Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="5b24c-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b24c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b24c-109">Requirements</span></span>  
 <span data-ttu-id="5b24c-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b24c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b24c-111">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="5b24c-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5b24c-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5b24c-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b24c-113">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b24c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b24c-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="5b24c-114">See also</span></span>

- [<span data-ttu-id="5b24c-115">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5b24c-115">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
