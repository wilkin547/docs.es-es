---
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
ms.openlocfilehash: 3059d30f3969b4e19cee5a8d7a34c606f3849c05
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008747"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="47a66-102">IMetaDataEmit::SetRVA (Método)</span><span class="sxs-lookup"><span data-stu-id="47a66-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="47a66-103">Establece la dirección virtual relativa del método especificado.</span><span class="sxs-lookup"><span data-stu-id="47a66-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47a66-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47a66-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,
    [in]  ULONG        ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47a66-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47a66-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="47a66-106">de Token para la implementación del método o método de destino.</span><span class="sxs-lookup"><span data-stu-id="47a66-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="47a66-107">de Dirección del código o área de datos.</span><span class="sxs-lookup"><span data-stu-id="47a66-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47a66-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47a66-108">Requirements</span></span>  
 <span data-ttu-id="47a66-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47a66-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47a66-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="47a66-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47a66-111">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="47a66-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47a66-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47a66-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a66-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47a66-113">See also</span></span>

- [<span data-ttu-id="47a66-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="47a66-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="47a66-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="47a66-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
