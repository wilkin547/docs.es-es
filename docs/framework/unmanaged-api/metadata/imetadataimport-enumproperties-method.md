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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 410fd7a702d3aa3812b4ea053c43fdaa507a474a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176043"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="e256e-102">IMetaDataImport::EnumProperties (Método)</span><span class="sxs-lookup"><span data-stu-id="e256e-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="e256e-103">Enumera los tokens de PropertyDef que representan las propiedades del tipo al que hace referencia el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="e256e-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e256e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e256e-104">Syntax</span></span>  
  
```  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e256e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e256e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e256e-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="e256e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="e256e-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="e256e-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="e256e-108">[in] Un token de TypeDef que representa el tipo con propiedades a enumerar.</span><span class="sxs-lookup"><span data-stu-id="e256e-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="e256e-109">[out] Matriz utilizada para almacenar los tokens de PropertyDef.</span><span class="sxs-lookup"><span data-stu-id="e256e-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e256e-110">[in] Tamaño máximo de la matriz `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="e256e-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="e256e-111">[out] El número de tokens de PropertyDef devueltos en `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="e256e-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e256e-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e256e-112">Return Value</span></span>  
  
|<span data-ttu-id="e256e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e256e-113">HRESULT</span></span>|<span data-ttu-id="e256e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="e256e-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumProperties` <span data-ttu-id="e256e-115">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e256e-115">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e256e-116">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="e256e-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="e256e-117">En ese caso, `pcProperties` es cero.</span><span class="sxs-lookup"><span data-stu-id="e256e-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e256e-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e256e-118">Requirements</span></span>  
 <span data-ttu-id="e256e-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e256e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e256e-120">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="e256e-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e256e-121">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e256e-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e256e-122">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e256e-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e256e-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e256e-123">See also</span></span>

- [<span data-ttu-id="e256e-124">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e256e-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e256e-125">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e256e-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
