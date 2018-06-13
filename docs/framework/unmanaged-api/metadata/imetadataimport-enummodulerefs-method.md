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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 294156983507476b7ddfda3bc3cad16bb32f422b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445414"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="9ba18-102">IMetaDataImport::EnumModuleRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="9ba18-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="9ba18-103">Enumera los tokens de ModuleRef que representan los módulos importados.</span><span class="sxs-lookup"><span data-stu-id="9ba18-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ba18-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ba18-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ba18-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9ba18-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="9ba18-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="9ba18-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="9ba18-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="9ba18-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="9ba18-108">[out] Matriz utilizada para almacenar los tokens de ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="9ba18-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9ba18-109">[in] Tamaño máximo de la matriz `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="9ba18-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="9ba18-110">[out] El número de tokens de ModuleRef devueltos en `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="9ba18-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ba18-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9ba18-111">Return Value</span></span>  
  
|<span data-ttu-id="9ba18-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ba18-112">HRESULT</span></span>|<span data-ttu-id="9ba18-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ba18-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9ba18-114">`EnumModuleRefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9ba18-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9ba18-115">No hay ningún tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="9ba18-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="9ba18-116">En ese caso, `pcModuleRefs` es cero.</span><span class="sxs-lookup"><span data-stu-id="9ba18-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9ba18-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ba18-117">Requirements</span></span>  
 <span data-ttu-id="9ba18-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ba18-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ba18-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9ba18-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9ba18-120">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ba18-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9ba18-121">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ba18-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ba18-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ba18-122">See Also</span></span>  
 [<span data-ttu-id="9ba18-123">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ba18-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="9ba18-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ba18-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
