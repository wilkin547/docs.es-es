---
title: "IMetaDataImport::CloseEnum (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.CloseEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::CloseEnum
helpviewer_keywords:
- IMetaDataImport::CloseEnum method [.NET Framework metadata]
- CloseEnum method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 727819d5-1dab-4ebb-ac25-950b4111dc72
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 80e156cd92519fc78f2a3076d03b279b7a63c1d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="8447c-102">IMetaDataImport::CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="8447c-102">IMetaDataImport::CloseEnum Method</span></span>
<span data-ttu-id="8447c-103">Cierra el enumerador identificado por el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="8447c-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8447c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8447c-104">Syntax</span></span>  
  
```  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8447c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8447c-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="8447c-106">[in] El identificador para el enumerador cerrar.</span><span class="sxs-lookup"><span data-stu-id="8447c-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8447c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8447c-107">Remarks</span></span>  
 <span data-ttu-id="8447c-108">El identificador especificado por `hEnum` se obtiene del anterior `Enum` *nombre* llamadas (por ejemplo, [IMetaDataImport:: EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="8447c-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8447c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8447c-109">Requirements</span></span>  
 <span data-ttu-id="8447c-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8447c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8447c-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8447c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8447c-112">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8447c-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8447c-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8447c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8447c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8447c-114">See Also</span></span>  
 [<span data-ttu-id="8447c-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8447c-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="8447c-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8447c-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
