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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123874"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="ff5f4-102">IMetaDataImport::CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="ff5f4-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="ff5f4-103">Cierra el enumerador que se identifica por el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="ff5f4-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff5f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff5f4-104">Syntax</span></span>  
  
```  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff5f4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff5f4-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="ff5f4-106">[in] El identificador para el enumerador cerrar.</span><span class="sxs-lookup"><span data-stu-id="ff5f4-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff5f4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff5f4-107">Remarks</span></span>  
 <span data-ttu-id="ff5f4-108">El identificador especificado por `hEnum` se obtiene un anterior `Enum` *nombre* llamar (por ejemplo, [EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="ff5f4-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff5f4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff5f4-109">Requirements</span></span>  
 <span data-ttu-id="ff5f4-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff5f4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff5f4-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="ff5f4-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ff5f4-112">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff5f4-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="ff5f4-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ff5f4-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ff5f4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff5f4-114">See also</span></span>

- [<span data-ttu-id="ff5f4-115">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff5f4-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ff5f4-116">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff5f4-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
