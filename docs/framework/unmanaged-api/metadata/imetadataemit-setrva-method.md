---
description: 'Más información sobre: IMetaDataEmit:: SetRVA ((método)'
title: IMetaDataEmit::SetRVA (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
ms.openlocfilehash: 52294250df2b7a677bb4ecb09ea0a97baca595a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771787"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="6f3bf-103">IMetaDataEmit::SetRVA (Método)</span><span class="sxs-lookup"><span data-stu-id="6f3bf-103">IMetaDataEmit::SetRVA Method</span></span>

<span data-ttu-id="6f3bf-104">Establece la dirección virtual relativa del método especificado.</span><span class="sxs-lookup"><span data-stu-id="6f3bf-104">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f3bf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f3bf-105">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,
    [in]  ULONG        ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f3bf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6f3bf-106">Parameters</span></span>  

 `md`  
 <span data-ttu-id="6f3bf-107">de Token para la implementación del método o método de destino.</span><span class="sxs-lookup"><span data-stu-id="6f3bf-107">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="6f3bf-108">de Dirección del código o área de datos.</span><span class="sxs-lookup"><span data-stu-id="6f3bf-108">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f3bf-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6f3bf-109">Requirements</span></span>  

 <span data-ttu-id="6f3bf-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f3bf-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f3bf-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6f3bf-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6f3bf-112">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6f3bf-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f3bf-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f3bf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f3bf-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f3bf-114">See also</span></span>

- [<span data-ttu-id="6f3bf-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6f3bf-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="6f3bf-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6f3bf-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
