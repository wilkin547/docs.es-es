---
title: IMetaDataImport::EnumModuleRefs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumModuleRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumModuleRefs
helpviewer_keywords:
- EnumModuleRefs method [.NET Framework metadata]
- IMetaDataImport::EnumModuleRefs method [.NET Framework metadata]
ms.assetid: 53441f3a-68d2-477c-906e-37c55dfcfb4d
topic_type:
- apiref
ms.openlocfilehash: 788fd1815415bf8bcfa20d431a5451679d2025bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728282"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="18667-102">IMetaDataImport::EnumModuleRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="18667-102">IMetaDataImport::EnumModuleRefs Method</span></span>

<span data-ttu-id="18667-103">Enumera los tokens de ModuleRef que representan los módulos importados.</span><span class="sxs-lookup"><span data-stu-id="18667-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18667-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18667-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18667-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="18667-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="18667-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="18667-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="18667-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="18667-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="18667-108">enuncia Matriz utilizada para almacenar los tokens de ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="18667-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="18667-109">[in] Tamaño máximo de la matriz `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="18667-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="18667-110">enuncia El número de tokens de ModuleRef devueltos en `rModuleRefs` .</span><span class="sxs-lookup"><span data-stu-id="18667-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18667-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="18667-111">Return Value</span></span>  
  
|<span data-ttu-id="18667-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="18667-112">HRESULT</span></span>|<span data-ttu-id="18667-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="18667-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="18667-114">`EnumModuleRefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="18667-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="18667-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="18667-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="18667-116">En ese caso, `pcModuleRefs` es cero.</span><span class="sxs-lookup"><span data-stu-id="18667-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18667-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18667-117">Requirements</span></span>  

 <span data-ttu-id="18667-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18667-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18667-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="18667-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="18667-120">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="18667-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="18667-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18667-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18667-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18667-122">See also</span></span>

- [<span data-ttu-id="18667-123">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="18667-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="18667-124">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="18667-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
