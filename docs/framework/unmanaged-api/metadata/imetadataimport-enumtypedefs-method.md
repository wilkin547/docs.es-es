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
ms.openlocfilehash: 0e6314a76433276561a8b4b87a852464dae69824
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656263"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="3b6e2-102">IMetaDataImport::EnumTypeDefs (Método)</span><span class="sxs-lookup"><span data-stu-id="3b6e2-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="3b6e2-103">Enumera los tokens de TypeDef que representan todos los tipos en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="3b6e2-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b6e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b6e2-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b6e2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b6e2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3b6e2-106">[out] Un puntero al nuevo enumerador.</span><span class="sxs-lookup"><span data-stu-id="3b6e2-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="3b6e2-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="3b6e2-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="3b6e2-108">[in] Matriz utilizada para almacenar los tokens de TypeDef.</span><span class="sxs-lookup"><span data-stu-id="3b6e2-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3b6e2-109">[in] Tamaño máximo de la matriz `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="3b6e2-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="3b6e2-110">[out] El número de tokens de TypeDef devueltos en `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="3b6e2-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b6e2-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3b6e2-111">Return Value</span></span>  
  
|<span data-ttu-id="3b6e2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3b6e2-112">HRESULT</span></span>|<span data-ttu-id="3b6e2-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b6e2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3b6e2-114">`EnumTypeDefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3b6e2-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3b6e2-115">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="3b6e2-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="3b6e2-116">En ese caso, `pcTypeDefs` es cero.</span><span class="sxs-lookup"><span data-stu-id="3b6e2-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b6e2-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b6e2-117">Remarks</span></span>  
 <span data-ttu-id="3b6e2-118">El token de TypeDef representa un tipo como una clase o una interfaz, así como cualquier tipo de agregado a través de un mecanismo de extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="3b6e2-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b6e2-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b6e2-119">Requirements</span></span>  
 <span data-ttu-id="3b6e2-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b6e2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b6e2-121">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="3b6e2-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b6e2-122">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3b6e2-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3b6e2-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b6e2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b6e2-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b6e2-124">See also</span></span>
- [<span data-ttu-id="3b6e2-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b6e2-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3b6e2-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b6e2-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
