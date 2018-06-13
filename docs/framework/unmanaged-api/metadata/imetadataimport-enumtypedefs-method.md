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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53ed486a885514d02bf2be9c473e102c2c5f0e15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446848"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="ecf02-102">IMetaDataImport::EnumTypeDefs (Método)</span><span class="sxs-lookup"><span data-stu-id="ecf02-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="ecf02-103">Enumera los tokens de TypeDef que representan todos los tipos en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="ecf02-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecf02-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ecf02-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecf02-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ecf02-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ecf02-106">[out] Un puntero al nuevo enumerador.</span><span class="sxs-lookup"><span data-stu-id="ecf02-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="ecf02-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="ecf02-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="ecf02-108">[in] Matriz utilizada para almacenar los tokens de TypeDef.</span><span class="sxs-lookup"><span data-stu-id="ecf02-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ecf02-109">[in] Tamaño máximo de la matriz `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="ecf02-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="ecf02-110">[out] El número de tokens de TypeDef devueltos en `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="ecf02-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ecf02-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ecf02-111">Return Value</span></span>  
  
|<span data-ttu-id="ecf02-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ecf02-112">HRESULT</span></span>|<span data-ttu-id="ecf02-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecf02-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ecf02-114">`EnumTypeDefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ecf02-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ecf02-115">No hay ningún tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="ecf02-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="ecf02-116">En ese caso, `pcTypeDefs` es cero.</span><span class="sxs-lookup"><span data-stu-id="ecf02-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecf02-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ecf02-117">Remarks</span></span>  
 <span data-ttu-id="ecf02-118">El token de TypeDef representa un tipo como una clase o una interfaz, así como cualquier tipo de agregado a través de un mecanismo de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="ecf02-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecf02-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ecf02-119">Requirements</span></span>  
 <span data-ttu-id="ecf02-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecf02-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecf02-121">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ecf02-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ecf02-122">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ecf02-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ecf02-123">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecf02-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecf02-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecf02-124">See Also</span></span>  
 [<span data-ttu-id="ecf02-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ecf02-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ecf02-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ecf02-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
