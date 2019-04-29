---
title: IMetaDataImport::GetClassLayout (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11748d3ad99c4050045cce3786eec5604c02ac0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777837"
---
# <a name="imetadataimportgetclasslayout-method"></a><span data-ttu-id="90887-102">IMetaDataImport::GetClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="90887-102">IMetaDataImport::GetClassLayout Method</span></span>
<span data-ttu-id="90887-103">Obtiene la información de diseño de la clase a la que hace referencia el token TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="90887-103">Gets layout information for the class referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90887-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90887-104">Syntax</span></span>  
  
```  
HRESULT GetClassLayout  (   
   [in]  mdTypeDef          td,   
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90887-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="90887-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="90887-106">[in] El token de TypeDef para la clase con el diseño para devolver.</span><span class="sxs-lookup"><span data-stu-id="90887-106">[in] The TypeDef token for the class with the layout to return.</span></span>  
  
 `pdwPackSize`  
 <span data-ttu-id="90887-107">[out] Uno de los valores 1, 2, 4, 8 o 16, que representa el tamaño del paquete de la clase.</span><span class="sxs-lookup"><span data-stu-id="90887-107">[out] One of the values 1, 2, 4, 8, or 16, representing the pack size of the class.</span></span>  
  
 `rFieldOffset`  
 <span data-ttu-id="90887-108">[out] Una matriz de [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) valores.</span><span class="sxs-lookup"><span data-stu-id="90887-108">[out] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) values.</span></span>  
  
 `cMax`  
 <span data-ttu-id="90887-109">[in] Tamaño máximo de la matriz `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="90887-109">[in] The maximum size of the `rFieldOffset` array.</span></span>  
  
 `pcFieldOffset`  
 <span data-ttu-id="90887-110">[out] El número de elementos devueltos en `rFieldOffset`.</span><span class="sxs-lookup"><span data-stu-id="90887-110">[out] The number of elements returned in `rFieldOffset`.</span></span>  
  
 `pulClassSize`  
 <span data-ttu-id="90887-111">[out] El tamaño en bytes de la clase representada por `td`.</span><span class="sxs-lookup"><span data-stu-id="90887-111">[out] The size in bytes of the class represented by `td`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90887-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90887-112">Requirements</span></span>  
 <span data-ttu-id="90887-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90887-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90887-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="90887-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90887-115">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="90887-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="90887-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90887-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90887-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="90887-117">See also</span></span>

- [<span data-ttu-id="90887-118">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="90887-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="90887-119">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="90887-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
