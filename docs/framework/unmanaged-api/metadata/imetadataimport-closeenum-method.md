---
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
ms.openlocfilehash: 4347a4da3e58a20c98e217de3a71c448e244eb29
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440120"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="062fd-102">IMetaDataImport::CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="062fd-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="062fd-103">Cierra el enumerador identificado por el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="062fd-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="062fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="062fd-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="062fd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="062fd-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="062fd-106">de Identificador del enumerador que se va a cerrar.</span><span class="sxs-lookup"><span data-stu-id="062fd-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="062fd-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="062fd-107">Remarks</span></span>  
 <span data-ttu-id="062fd-108">El identificador especificado por `hEnum` se obtiene a partir de una llamada de *nombre* de `Enum`anterior (por ejemplo, [IMetaDataImport:: enumtypedefs (](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="062fd-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="062fd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="062fd-109">Requirements</span></span>  
 <span data-ttu-id="062fd-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="062fd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="062fd-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="062fd-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="062fd-112">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="062fd-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="062fd-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="062fd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="062fd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="062fd-114">See also</span></span>

- [<span data-ttu-id="062fd-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="062fd-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="062fd-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="062fd-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
