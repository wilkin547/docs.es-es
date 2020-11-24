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
ms.openlocfilehash: 6ee87fdbf75d4a07a7337a1c9fdc58a06191b992
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674832"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="5f8f5-102">ICLRStrongName::StrongNameHashSize (Método)</span><span class="sxs-lookup"><span data-stu-id="5f8f5-102">ICLRStrongName::StrongNameHashSize Method</span></span>

<span data-ttu-id="5f8f5-103">Obtiene el tamaño de búfer necesario para un hash mediante el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="5f8f5-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f8f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f8f5-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f8f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f8f5-105">Parameters</span></span>  

 `ulHashAlg`  
 <span data-ttu-id="5f8f5-106">de Algoritmo hash que se usa para calcular el tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="5f8f5-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="5f8f5-107">enuncia Tamaño de búfer devuelto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="5f8f5-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f8f5-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5f8f5-108">Return Value</span></span>  

 <span data-ttu-id="5f8f5-109">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="5f8f5-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f8f5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f8f5-110">Requirements</span></span>  

 <span data-ttu-id="5f8f5-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f8f5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f8f5-112">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="5f8f5-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5f8f5-113">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f8f5-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f8f5-114">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f8f5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f8f5-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5f8f5-115">See also</span></span>

- [<span data-ttu-id="5f8f5-116">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f8f5-116">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
