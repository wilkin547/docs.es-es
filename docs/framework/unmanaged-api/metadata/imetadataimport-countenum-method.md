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
ms.openlocfilehash: f2470cd7112adff35ef49c21a155072fcd4008be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727294"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="32456-102">IMetaDataImport::CountEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="32456-102">IMetaDataImport::CountEnum Method</span></span>

<span data-ttu-id="32456-103">Obtiene el número de elementos de la enumeración recuperados por el enumerador especificado.</span><span class="sxs-lookup"><span data-stu-id="32456-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32456-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32456-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32456-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="32456-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="32456-106">de Identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="32456-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="32456-107">enuncia Número de elementos enumerados.</span><span class="sxs-lookup"><span data-stu-id="32456-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32456-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="32456-108">Remarks</span></span>  

 <span data-ttu-id="32456-109">El identificador especificado por `hEnum` se obtiene a partir de una llamada de `Enum` *nombre* anterior (por ejemplo, [IMetaDataImport:: enumtypedefs (](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="32456-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32456-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="32456-110">Requirements</span></span>  

 <span data-ttu-id="32456-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32456-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32456-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="32456-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="32456-113">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="32456-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="32456-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32456-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32456-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="32456-115">See also</span></span>

- [<span data-ttu-id="32456-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="32456-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="32456-117">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="32456-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
