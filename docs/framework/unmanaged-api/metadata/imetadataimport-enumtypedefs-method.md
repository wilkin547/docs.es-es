---
description: 'Más información sobre: IMetaDataImport:: Enumtypedefs ((método)'
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
ms.openlocfilehash: 28bd06b70573b780b687da9de0e13e17c29bb39a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670691"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="a302c-103">IMetaDataImport::EnumTypeDefs (Método)</span><span class="sxs-lookup"><span data-stu-id="a302c-103">IMetaDataImport::EnumTypeDefs Method</span></span>

<span data-ttu-id="a302c-104">Enumera los tokens de TypeDef que representan todos los tipos en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="a302c-104">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a302c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a302c-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a302c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a302c-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="a302c-107">enuncia Puntero al nuevo enumerador.</span><span class="sxs-lookup"><span data-stu-id="a302c-107">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="a302c-108">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="a302c-108">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="a302c-109">de Matriz que se usa para almacenar los tokens TypeDef.</span><span class="sxs-lookup"><span data-stu-id="a302c-109">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a302c-110">[in] Tamaño máximo de la matriz `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="a302c-110">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="a302c-111">enuncia El número de tokens TypeDef devueltos en `rTypeDefs` .</span><span class="sxs-lookup"><span data-stu-id="a302c-111">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a302c-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a302c-112">Return Value</span></span>  
  
|<span data-ttu-id="a302c-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a302c-113">HRESULT</span></span>|<span data-ttu-id="a302c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a302c-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a302c-115">`EnumTypeDefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a302c-115">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a302c-116">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="a302c-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="a302c-117">En ese caso, `pcTypeDefs` es cero.</span><span class="sxs-lookup"><span data-stu-id="a302c-117">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a302c-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a302c-118">Remarks</span></span>  

 <span data-ttu-id="a302c-119">El token TypeDef representa un tipo como una clase o una interfaz, así como cualquier tipo agregado a través de un mecanismo de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="a302c-119">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a302c-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a302c-120">Requirements</span></span>  

 <span data-ttu-id="a302c-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a302c-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a302c-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a302c-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a302c-123">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a302c-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a302c-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a302c-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a302c-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a302c-125">See also</span></span>

- [<span data-ttu-id="a302c-126">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a302c-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a302c-127">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a302c-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
