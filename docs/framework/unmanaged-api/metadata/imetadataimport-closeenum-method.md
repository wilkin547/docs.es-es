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
ms.openlocfilehash: f418b48f1b62ae8093197d64ca44b2ef659990a3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701723"
---
# <a name="imetadataimportcloseenum-method"></a><span data-ttu-id="55d85-102">IMetaDataImport::CloseEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="55d85-102">IMetaDataImport::CloseEnum Method</span></span>

<span data-ttu-id="55d85-103">Cierra el enumerador identificado por el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="55d85-103">Closes the enumerator that is identified by the specified handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55d85-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55d85-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
   [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55d85-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55d85-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="55d85-106">de Identificador del enumerador que se va a cerrar.</span><span class="sxs-lookup"><span data-stu-id="55d85-106">[in] The handle for the enumerator to close.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55d85-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="55d85-107">Remarks</span></span>  

 <span data-ttu-id="55d85-108">El identificador especificado por `hEnum` se obtiene a partir de una llamada de `Enum` *nombre* anterior (por ejemplo, [IMetaDataImport:: enumtypedefs (](imetadataimport-enumtypedefs-method.md)).</span><span class="sxs-lookup"><span data-stu-id="55d85-108">The handle specified by `hEnum` is obtained from a previous `Enum`*Name* call (for example, [IMetaDataImport::EnumTypeDefs](imetadataimport-enumtypedefs-method.md)).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55d85-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55d85-109">Requirements</span></span>  

 <span data-ttu-id="55d85-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55d85-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55d85-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="55d85-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="55d85-112">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55d85-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="55d85-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55d85-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d85-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="55d85-114">See also</span></span>

- [<span data-ttu-id="55d85-115">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="55d85-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="55d85-116">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="55d85-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
