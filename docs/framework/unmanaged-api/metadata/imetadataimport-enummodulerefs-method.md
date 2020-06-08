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
ms.openlocfilehash: fe7350e6d8e400ae37b5b8b7854a56f3c5c53ea7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491766"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="81f5a-102">IMetaDataImport::EnumModuleRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="81f5a-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="81f5a-103">Enumera los tokens de ModuleRef que representan los módulos importados.</span><span class="sxs-lookup"><span data-stu-id="81f5a-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81f5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81f5a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81f5a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81f5a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="81f5a-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="81f5a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="81f5a-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="81f5a-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="81f5a-108">enuncia Matriz utilizada para almacenar los tokens de ModuleRef.</span><span class="sxs-lookup"><span data-stu-id="81f5a-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="81f5a-109">[in] Tamaño máximo de la matriz `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="81f5a-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="81f5a-110">enuncia El número de tokens de ModuleRef devueltos en `rModuleRefs` .</span><span class="sxs-lookup"><span data-stu-id="81f5a-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81f5a-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="81f5a-111">Return Value</span></span>  
  
|<span data-ttu-id="81f5a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81f5a-112">HRESULT</span></span>|<span data-ttu-id="81f5a-113">Description</span><span class="sxs-lookup"><span data-stu-id="81f5a-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="81f5a-114">`EnumModuleRefs`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="81f5a-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="81f5a-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="81f5a-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="81f5a-116">En ese caso, `pcModuleRefs` es cero.</span><span class="sxs-lookup"><span data-stu-id="81f5a-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81f5a-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81f5a-117">Requirements</span></span>  
 <span data-ttu-id="81f5a-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81f5a-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81f5a-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="81f5a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="81f5a-120">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="81f5a-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="81f5a-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81f5a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81f5a-122">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="81f5a-122">See also</span></span>

- [<span data-ttu-id="81f5a-123">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="81f5a-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="81f5a-124">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="81f5a-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
