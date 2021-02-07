---
description: 'Más información sobre: IMetaDataImport:: Closeenum ((método)'
title: IMetaDataImport::CloseEnum (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::CloseEnum
helpviewer_keywords:
- IMetaDataImport::CloseEnum method [.NET Framework metadata]
- CloseEnum method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 727819d5-1dab-4ebb-ac25-950b4111dc72
topic_type:
- apiref
ms.openlocfilehash: b18b484cab0d9f4c0ecea21da78535c9a872bb1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677748"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="edddc-103">IMetaDataImport::CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="edddc-103">IMetaDataImport::CloseEnum Method</span></span>

<span data-ttu-id="edddc-104">Cierra el enumerador identificado por el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="edddc-104">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edddc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="edddc-105">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edddc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="edddc-106">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="edddc-107">de Identificador del enumerador que se va a cerrar.</span><span class="sxs-lookup"><span data-stu-id="edddc-107">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edddc-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="edddc-108">Remarks</span></span>  

 <span data-ttu-id="edddc-109">El identificador especificado por `hEnum` se obtiene a partir de una llamada de `Enum` *nombre* anterior (por ejemplo, [IMetaDataImport:: enumtypedefs (](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="edddc-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edddc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="edddc-110">Requirements</span></span>  

 <span data-ttu-id="edddc-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edddc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edddc-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="edddc-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="edddc-113">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="edddc-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="edddc-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edddc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edddc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="edddc-115">See also</span></span>

- [<span data-ttu-id="edddc-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="edddc-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="edddc-117">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="edddc-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
