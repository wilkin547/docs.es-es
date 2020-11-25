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
ms.openlocfilehash: 4545f5f8d78e588c655a72340210a785b0feb619
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720417"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="b8441-102">IMetaDataImport::EnumTypeDefs (Método)</span><span class="sxs-lookup"><span data-stu-id="b8441-102">IMetaDataImport::EnumTypeDefs Method</span></span>

<span data-ttu-id="b8441-103">Enumera los tokens de TypeDef que representan todos los tipos en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="b8441-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8441-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8441-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8441-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8441-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="b8441-106">enuncia Puntero al nuevo enumerador.</span><span class="sxs-lookup"><span data-stu-id="b8441-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="b8441-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="b8441-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="b8441-108">de Matriz que se usa para almacenar los tokens TypeDef.</span><span class="sxs-lookup"><span data-stu-id="b8441-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b8441-109">[in] Tamaño máximo de la matriz `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="b8441-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="b8441-110">enuncia El número de tokens TypeDef devueltos en `rTypeDefs` .</span><span class="sxs-lookup"><span data-stu-id="b8441-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8441-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b8441-111">Return Value</span></span>  
  
|<span data-ttu-id="b8441-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b8441-112">HRESULT</span></span>|<span data-ttu-id="b8441-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8441-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b8441-114">`EnumTypeDefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b8441-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b8441-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="b8441-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="b8441-116">En ese caso, `pcTypeDefs` es cero.</span><span class="sxs-lookup"><span data-stu-id="b8441-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8441-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8441-117">Remarks</span></span>  

 <span data-ttu-id="b8441-118">El token TypeDef representa un tipo como una clase o una interfaz, así como cualquier tipo agregado a través de un mecanismo de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="b8441-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8441-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8441-119">Requirements</span></span>  

 <span data-ttu-id="b8441-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8441-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8441-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b8441-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b8441-122">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b8441-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b8441-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8441-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8441-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b8441-124">See also</span></span>

- [<span data-ttu-id="b8441-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8441-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="b8441-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8441-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
