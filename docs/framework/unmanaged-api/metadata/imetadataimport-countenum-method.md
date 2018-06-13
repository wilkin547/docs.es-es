---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a8e30020a8296e037d1dacc8dbaabde7e40032e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445291"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="a0664-102">IMetaDataImport::CountEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="a0664-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="a0664-103">Obtiene el número de elementos de la enumeración recuperada por el enumerador especificado.</span><span class="sxs-lookup"><span data-stu-id="a0664-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0664-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0664-104">Syntax</span></span>  
  
```  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,   
   [out] ULONG       *pulCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0664-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a0664-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="a0664-106">[in] El identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="a0664-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="a0664-107">[out] El número de elementos enumerados.</span><span class="sxs-lookup"><span data-stu-id="a0664-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0664-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0664-108">Remarks</span></span>  
 <span data-ttu-id="a0664-109">El identificador especificado por `hEnum` se obtiene del anterior `Enum` *nombre* llamadas (por ejemplo, [IMetaDataImport:: EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="a0664-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0664-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0664-110">Requirements</span></span>  
 <span data-ttu-id="a0664-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0664-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0664-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a0664-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0664-113">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0664-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a0664-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0664-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0664-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0664-115">See Also</span></span>  
 [<span data-ttu-id="a0664-116">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0664-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a0664-117">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0664-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
