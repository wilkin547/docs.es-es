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
ms.openlocfilehash: 4d246e3046cda9031689e625a0c3b054cbcf9f6e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465951"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="af919-102">ICLRStrongName::StrongNameHashSize (Método)</span><span class="sxs-lookup"><span data-stu-id="af919-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="af919-103">Obtiene el tamaño de búfer necesario para un hash mediante el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="af919-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af919-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af919-104">Syntax</span></span>  
  
```  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af919-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af919-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="af919-106">[in] El algoritmo hash utilizado para calcular el tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="af919-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="af919-107">[out] El tamaño del búfer devuelto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="af919-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af919-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="af919-108">Return Value</span></span>  
 <span data-ttu-id="af919-109">`S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="af919-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af919-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af919-110">Requirements</span></span>  
 <span data-ttu-id="af919-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af919-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af919-112">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="af919-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="af919-113">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="af919-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af919-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af919-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af919-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="af919-115">See also</span></span>
- [<span data-ttu-id="af919-116">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af919-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
