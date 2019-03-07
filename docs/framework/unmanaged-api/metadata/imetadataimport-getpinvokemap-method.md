---
title: IMetaDataImport::GetPinvokeMap (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ec32b285713e3e506359c4c831eb076d2b47a967
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499788"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="ec4e2-102">IMetaDataImport::GetPinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="ec4e2-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="ec4e2-103">Obtiene un token ModuleRef para representar el ensamblado de destino de una llamada PInvoke.</span><span class="sxs-lookup"><span data-stu-id="ec4e2-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec4e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec4e2-104">Syntax</span></span>  
  
```  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec4e2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec4e2-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ec4e2-106">[in] Un token de FieldDef o MethodDef para obtener los metadatos de asignación de PInvoke.</span><span class="sxs-lookup"><span data-stu-id="ec4e2-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="ec4e2-107">[out] Un puntero a los marcadores utilizados para la asignación.</span><span class="sxs-lookup"><span data-stu-id="ec4e2-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="ec4e2-108">Este valor es una máscara de bits desde el [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="ec4e2-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="ec4e2-109">[out] El nombre de la DLL de destino no administrado.</span><span class="sxs-lookup"><span data-stu-id="ec4e2-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="ec4e2-110">[in] El tamaño en caracteres anchos de `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="ec4e2-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="ec4e2-111">[out] El número de caracteres anchos que se devuelven en `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="ec4e2-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="ec4e2-112">[out] Un puntero a un token ModuleRef que representa la biblioteca de objetos de destino no administrado.</span><span class="sxs-lookup"><span data-stu-id="ec4e2-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec4e2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec4e2-113">Requirements</span></span>  
 <span data-ttu-id="ec4e2-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec4e2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec4e2-115">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="ec4e2-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec4e2-116">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ec4e2-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec4e2-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec4e2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec4e2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec4e2-118">See also</span></span>
- [<span data-ttu-id="ec4e2-119">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec4e2-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ec4e2-120">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec4e2-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
