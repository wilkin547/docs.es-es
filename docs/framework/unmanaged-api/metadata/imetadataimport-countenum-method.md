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
ms.openlocfilehash: 4521a3f15ec358a4d786a4533efb6b99d0e1c1cc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492387"
---
# <a name="imetadataimportcountenum-method"></a><span data-ttu-id="cc974-102">IMetaDataImport::CountEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="cc974-102">IMetaDataImport::CountEnum Method</span></span>
<span data-ttu-id="cc974-103">Obtiene el número de elementos de la enumeración recuperados por el enumerador especificado.</span><span class="sxs-lookup"><span data-stu-id="cc974-103">Gets the number of elements in the enumeration that was retrieved by the specified enumerator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc974-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc974-104">Syntax</span></span>  
  
```cpp  
HRESULT CountEnum (  
   [in]  HCORENUM    hEnum,
   [out] ULONG       *pulCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc974-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cc974-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="cc974-106">de Identificador del enumerador.</span><span class="sxs-lookup"><span data-stu-id="cc974-106">[in] The handle for the enumerator.</span></span>  
  
 `pulCount`  
 <span data-ttu-id="cc974-107">enuncia Número de elementos enumerados.</span><span class="sxs-lookup"><span data-stu-id="cc974-107">[out] The number of elements enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc974-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc974-108">Remarks</span></span>  
 <span data-ttu-id="cc974-109">El identificador especificado por `hEnum` se obtiene a partir de una llamada de `Enum` *nombre* anterior (por ejemplo, [IMetaDataImport:: enumtypedefs (](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="cc974-109">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc974-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc974-110">Requirements</span></span>  
 <span data-ttu-id="cc974-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc974-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc974-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cc974-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc974-113">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cc974-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cc974-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc974-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc974-115">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="cc974-115">See also</span></span>

- [<span data-ttu-id="cc974-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cc974-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="cc974-117">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cc974-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
