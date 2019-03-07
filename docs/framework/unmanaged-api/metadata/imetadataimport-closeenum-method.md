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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dda94acc2ec5da456cdc41ba0902cdc414b11524
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486386"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="b1fb9-102">IMetaDataImport::CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="b1fb9-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="b1fb9-103">Cierra el enumerador que se identifica por el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="b1fb9-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1fb9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1fb9-104">Syntax</span></span>  
  
```  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1fb9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b1fb9-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="b1fb9-106">[in] El identificador para el enumerador cerrar.</span><span class="sxs-lookup"><span data-stu-id="b1fb9-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1fb9-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b1fb9-107">Remarks</span></span>  
 <span data-ttu-id="b1fb9-108">El identificador especificado por `hEnum` se obtiene un anterior `Enum` *nombre* llamar (por ejemplo, [EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="b1fb9-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1fb9-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b1fb9-109">Requirements</span></span>  
 <span data-ttu-id="b1fb9-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1fb9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1fb9-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b1fb9-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b1fb9-112">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b1fb9-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b1fb9-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1fb9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1fb9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1fb9-114">See also</span></span>
- [<span data-ttu-id="b1fb9-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b1fb9-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b1fb9-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b1fb9-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
