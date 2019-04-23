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
ms.openlocfilehash: 7846eeceeb4d59c4e9aae73c79172c89184396e0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123874"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="d1e27-102">IMetaDataImport::CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="d1e27-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="d1e27-103">Cierra el enumerador que se identifica por el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="d1e27-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1e27-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1e27-104">Syntax</span></span>  
  
```  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1e27-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d1e27-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="d1e27-106">[in] El identificador para el enumerador cerrar.</span><span class="sxs-lookup"><span data-stu-id="d1e27-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1e27-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d1e27-107">Remarks</span></span>  
 <span data-ttu-id="d1e27-108">El identificador especificado por `hEnum` se obtiene un anterior `Enum` *nombre* llamar (por ejemplo, [EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="d1e27-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1e27-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1e27-109">Requirements</span></span>  
 <span data-ttu-id="d1e27-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1e27-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1e27-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="d1e27-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d1e27-112">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d1e27-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d1e27-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1e27-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e27-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1e27-114">See also</span></span>

- [<span data-ttu-id="d1e27-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d1e27-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d1e27-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d1e27-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
