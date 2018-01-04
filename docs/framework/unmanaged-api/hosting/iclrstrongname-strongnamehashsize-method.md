---
title: "ICLRStrongName::StrongNameHashSize (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameHashSize
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: acc2812567ce2d47d3f06c000fc387708c2e8acb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="c10cc-102">ICLRStrongName::StrongNameHashSize (Método)</span><span class="sxs-lookup"><span data-stu-id="c10cc-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="c10cc-103">Obtiene el tamaño de búfer requerido para un hash mediante el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="c10cc-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c10cc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c10cc-104">Syntax</span></span>  
  
```  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c10cc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c10cc-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="c10cc-106">[in] El algoritmo hash que se utiliza para calcular el tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="c10cc-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="c10cc-107">[out] El tamaño de búfer devuelto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="c10cc-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c10cc-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c10cc-108">Return Value</span></span>  
 <span data-ttu-id="c10cc-109">`S_OK`Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="c10cc-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c10cc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c10cc-110">Requirements</span></span>  
 <span data-ttu-id="c10cc-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c10cc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c10cc-112">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c10cc-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c10cc-113">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c10cc-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c10cc-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c10cc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c10cc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c10cc-115">See Also</span></span>  
 [<span data-ttu-id="c10cc-116">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c10cc-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
