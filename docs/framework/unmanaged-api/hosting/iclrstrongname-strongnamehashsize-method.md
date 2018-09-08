---
title: ICLRStrongName::StrongNameHashSize (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c09832d296033b0790d3e6282763a1163abdfd2
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44217014"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="15851-102">ICLRStrongName::StrongNameHashSize (Método)</span><span class="sxs-lookup"><span data-stu-id="15851-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="15851-103">Obtiene el tamaño de búfer necesario para un hash mediante el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="15851-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15851-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15851-104">Syntax</span></span>  
  
```  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15851-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15851-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="15851-106">[in] El algoritmo hash utilizado para calcular el tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="15851-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="15851-107">[out] El tamaño del búfer devuelto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="15851-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15851-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="15851-108">Return Value</span></span>  
 <span data-ttu-id="15851-109">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="15851-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15851-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15851-110">Requirements</span></span>  
 <span data-ttu-id="15851-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15851-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15851-112">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="15851-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="15851-113">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15851-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15851-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15851-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15851-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="15851-115">See Also</span></span>  
 [<span data-ttu-id="15851-116">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="15851-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
