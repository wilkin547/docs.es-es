---
description: 'Más información sobre: ICLRStrongName:: Strongnamehashsize ((método)'
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
ms.openlocfilehash: 74781f0eaec720a84a242e6a9637036408652601
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799595"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="91da9-103">ICLRStrongName::StrongNameHashSize (Método)</span><span class="sxs-lookup"><span data-stu-id="91da9-103">ICLRStrongName::StrongNameHashSize Method</span></span>

<span data-ttu-id="91da9-104">Obtiene el tamaño de búfer necesario para un hash mediante el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="91da9-104">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91da9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91da9-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91da9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="91da9-106">Parameters</span></span>  

 `ulHashAlg`  
 <span data-ttu-id="91da9-107">de Algoritmo hash que se usa para calcular el tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="91da9-107">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="91da9-108">enuncia Tamaño de búfer devuelto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="91da9-108">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91da9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="91da9-109">Return Value</span></span>  

 <span data-ttu-id="91da9-110">`S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).</span><span class="sxs-lookup"><span data-stu-id="91da9-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91da9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91da9-111">Requirements</span></span>  

 <span data-ttu-id="91da9-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91da9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91da9-113">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="91da9-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="91da9-114">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="91da9-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91da9-115">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91da9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91da9-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91da9-116">See also</span></span>

- [<span data-ttu-id="91da9-117">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="91da9-117">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
