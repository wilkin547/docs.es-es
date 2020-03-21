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
ms.openlocfilehash: b780ca513d8a0b4f88e66594e86e9ff8290f6523
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177356"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="ead23-102">IMetaDataImport::CountEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="ead23-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="ead23-103">Obtiene el número de elementos de la enumeración que recuperó el enumerador especificado.</span><span class="sxs-lookup"><span data-stu-id="ead23-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ead23-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ead23-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ead23-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ead23-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="ead23-106">[en] El identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="ead23-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="ead23-107">[fuera] El número de elementos enumerados.</span><span class="sxs-lookup"><span data-stu-id="ead23-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ead23-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ead23-108">Remarks</span></span>  
 <span data-ttu-id="ead23-109">El identificador especificado `hEnum` por se obtiene `Enum`de una llamada *Name* anterior (por ejemplo, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="ead23-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ead23-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ead23-110">Requirements</span></span>  
 <span data-ttu-id="ead23-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ead23-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ead23-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ead23-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ead23-113">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ead23-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ead23-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ead23-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ead23-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ead23-115">See also</span></span>

- [<span data-ttu-id="ead23-116">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ead23-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ead23-117">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ead23-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
