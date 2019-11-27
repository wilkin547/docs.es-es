---
title: IMetaDataImport::EnumTypeDefs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
ms.openlocfilehash: 3854cb4aa3d229c87466c0a35a72447ceb235624
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449994"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="fd7d6-102">IMetaDataImport::EnumTypeDefs (Método)</span><span class="sxs-lookup"><span data-stu-id="fd7d6-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="fd7d6-103">Enumera los tokens de TypeDef que representan todos los tipos en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="fd7d6-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd7d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd7d6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd7d6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd7d6-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fd7d6-106">enuncia Puntero al nuevo enumerador.</span><span class="sxs-lookup"><span data-stu-id="fd7d6-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="fd7d6-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="fd7d6-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="fd7d6-108">de Matriz que se usa para almacenar los tokens TypeDef.</span><span class="sxs-lookup"><span data-stu-id="fd7d6-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fd7d6-109">[in] Tamaño máximo de la matriz `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="fd7d6-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="fd7d6-110">enuncia El número de tokens TypeDef devueltos en `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="fd7d6-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd7d6-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fd7d6-111">Return Value</span></span>  
  
|<span data-ttu-id="fd7d6-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd7d6-112">HRESULT</span></span>|<span data-ttu-id="fd7d6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd7d6-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fd7d6-114">`EnumTypeDefs` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="fd7d6-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fd7d6-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="fd7d6-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="fd7d6-116">En ese caso, `pcTypeDefs` es cero.</span><span class="sxs-lookup"><span data-stu-id="fd7d6-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd7d6-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd7d6-117">Remarks</span></span>  
 <span data-ttu-id="fd7d6-118">El token TypeDef representa un tipo como una clase o una interfaz, así como cualquier tipo agregado a través de un mecanismo de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="fd7d6-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd7d6-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd7d6-119">Requirements</span></span>  
 <span data-ttu-id="fd7d6-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd7d6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd7d6-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fd7d6-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd7d6-122">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fd7d6-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fd7d6-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd7d6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd7d6-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd7d6-124">See also</span></span>

- [<span data-ttu-id="fd7d6-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fd7d6-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="fd7d6-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fd7d6-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
