---
description: 'Más información sobre: IMetaDataImport:: EnumProperties ((método)'
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
ms.openlocfilehash: 7503dd14668e8ea4ccf8939e67b91a41db187105
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799361"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="ac007-103">IMetaDataImport::EnumProperties (Método)</span><span class="sxs-lookup"><span data-stu-id="ac007-103">IMetaDataImport::EnumProperties Method</span></span>

<span data-ttu-id="ac007-104">Enumera los tokens de PropertyDef que representan las propiedades del tipo al que hace referencia el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="ac007-104">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac007-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac007-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac007-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac007-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="ac007-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="ac007-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ac007-108">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="ac007-108">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="ac007-109">de Un token de TypeDef que representa el tipo con las propiedades que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="ac007-109">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="ac007-110">enuncia La matriz que se usa para almacenar los tokens de la cadena de la.</span><span class="sxs-lookup"><span data-stu-id="ac007-110">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ac007-111">[in] Tamaño máximo de la matriz `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="ac007-111">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="ac007-112">enuncia Número de tokens de la cadena de código devueltos en `rProperties` .</span><span class="sxs-lookup"><span data-stu-id="ac007-112">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac007-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ac007-113">Return Value</span></span>  
  
|<span data-ttu-id="ac007-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac007-114">HRESULT</span></span>|<span data-ttu-id="ac007-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac007-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ac007-116">`EnumProperties` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ac007-116">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ac007-117">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="ac007-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="ac007-118">En ese caso, `pcProperties` es cero.</span><span class="sxs-lookup"><span data-stu-id="ac007-118">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac007-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac007-119">Requirements</span></span>  

 <span data-ttu-id="ac007-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac007-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac007-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ac007-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac007-122">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac007-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac007-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac007-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac007-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac007-124">See also</span></span>

- [<span data-ttu-id="ac007-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac007-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ac007-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac007-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
