---
description: 'Más información sobre: IMetaDataImport:: Countenum ((método)'
title: IMetaDataImport::CountEnum (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CountEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CountEnum
helpviewer_keywords:
- CountEnum method [.NET Framework metadata]
- IMetaDataImport::CountEnum method [.NET Framework metadata]
ms.assetid: d1de53ad-9435-4b5f-9df7-07f21210e5b5
topic_type:
- apiref
ms.openlocfilehash: c579ef7ce440e3552ab28572fc6c96ad12d66400
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677696"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="d079d-103">IMetaDataImport::CountEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="d079d-103">IMetaDataImport::CountEnum Method</span></span>

<span data-ttu-id="d079d-104">Obtiene el número de elementos de la enumeración recuperados por el enumerador especificado.</span><span class="sxs-lookup"><span data-stu-id="d079d-104">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d079d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d079d-105">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d079d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d079d-106">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="d079d-107">de Identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="d079d-107">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="d079d-108">enuncia Número de elementos enumerados.</span><span class="sxs-lookup"><span data-stu-id="d079d-108">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d079d-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d079d-109">Remarks</span></span>  

 <span data-ttu-id="d079d-110">El identificador especificado por `hEnum` se obtiene a partir de una llamada de `Enum` *nombre* anterior (por ejemplo, [IMetaDataImport:: enumtypedefs (](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="d079d-110">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d079d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d079d-111">Requirements</span></span>  

 <span data-ttu-id="d079d-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d079d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d079d-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d079d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d079d-114">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d079d-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d079d-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d079d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d079d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d079d-116">See also</span></span>

- [<span data-ttu-id="d079d-117">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d079d-117">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="d079d-118">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d079d-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
