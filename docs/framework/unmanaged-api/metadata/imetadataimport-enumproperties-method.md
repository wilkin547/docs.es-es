---
title: IMetaDataImport::EnumProperties (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumProperties
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type:
- apiref
ms.openlocfilehash: 24ee37a36e34c74258e1c750ba424640c0496f0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728256"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="6e37f-102">IMetaDataImport::EnumProperties (Método)</span><span class="sxs-lookup"><span data-stu-id="6e37f-102">IMetaDataImport::EnumProperties Method</span></span>

<span data-ttu-id="6e37f-103">Enumera los tokens de PropertyDef que representan las propiedades del tipo al que hace referencia el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="6e37f-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e37f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e37f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e37f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6e37f-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="6e37f-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="6e37f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="6e37f-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="6e37f-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="6e37f-108">de Un token de TypeDef que representa el tipo con las propiedades que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="6e37f-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="6e37f-109">enuncia La matriz que se usa para almacenar los tokens de la cadena de la.</span><span class="sxs-lookup"><span data-stu-id="6e37f-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6e37f-110">[in] Tamaño máximo de la matriz `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="6e37f-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="6e37f-111">enuncia Número de tokens de la cadena de código devueltos en `rProperties` .</span><span class="sxs-lookup"><span data-stu-id="6e37f-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e37f-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6e37f-112">Return Value</span></span>  
  
|<span data-ttu-id="6e37f-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6e37f-113">HRESULT</span></span>|<span data-ttu-id="6e37f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e37f-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6e37f-115">`EnumProperties` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6e37f-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6e37f-116">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="6e37f-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="6e37f-117">En ese caso, `pcProperties` es cero.</span><span class="sxs-lookup"><span data-stu-id="6e37f-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6e37f-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6e37f-118">Requirements</span></span>  

 <span data-ttu-id="6e37f-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e37f-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e37f-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6e37f-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e37f-121">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6e37f-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6e37f-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e37f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e37f-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6e37f-123">See also</span></span>

- [<span data-ttu-id="6e37f-124">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6e37f-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6e37f-125">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6e37f-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
