---
description: 'Más información sobre: IMetaDataImport:: Enummodulerefs ((método)'
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
ms.openlocfilehash: 3e12d3da8ff556cb3add73ade77e11a68bf60223
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688824"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="0086c-103">IMetaDataImport::EnumModuleRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="0086c-103">IMetaDataImport::EnumModuleRefs Method</span></span>

<span data-ttu-id="0086c-104">Enumera los tokens de ModuleRef que representan los módulos importados.</span><span class="sxs-lookup"><span data-stu-id="0086c-104">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0086c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0086c-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0086c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0086c-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="0086c-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="0086c-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="0086c-108">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="0086c-108">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="0086c-109">enuncia Matriz utilizada para almacenar los tokens de ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="0086c-109">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0086c-110">[in] Tamaño máximo de la matriz `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="0086c-110">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="0086c-111">enuncia El número de tokens de ModuleRef devueltos en `rModuleRefs` .</span><span class="sxs-lookup"><span data-stu-id="0086c-111">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0086c-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0086c-112">Return Value</span></span>  
  
|<span data-ttu-id="0086c-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0086c-113">HRESULT</span></span>|<span data-ttu-id="0086c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="0086c-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0086c-115">`EnumModuleRefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0086c-115">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0086c-116">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="0086c-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="0086c-117">En ese caso, `pcModuleRefs` es cero.</span><span class="sxs-lookup"><span data-stu-id="0086c-117">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0086c-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0086c-118">Requirements</span></span>  

 <span data-ttu-id="0086c-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0086c-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0086c-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0086c-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0086c-121">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0086c-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0086c-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0086c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0086c-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0086c-123">See also</span></span>

- [<span data-ttu-id="0086c-124">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0086c-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="0086c-125">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0086c-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
