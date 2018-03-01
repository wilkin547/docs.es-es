---
title: "IMetaDataImport::GetPinvokeMap (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a28d628040a35d309515703563239a5f802dc4a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="6c459-102">IMetaDataImport::GetPinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="6c459-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="6c459-103">Obtiene un token ModuleRef para representar el ensamblado de destino de una llamada PInvoke.</span><span class="sxs-lookup"><span data-stu-id="6c459-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c459-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c459-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="6c459-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6c459-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="6c459-106">[in] Símbolo (token) de FieldDef o de MethodDef para obtener los metadatos de asignación de PInvoke.</span><span class="sxs-lookup"><span data-stu-id="6c459-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="6c459-107">[out] Un puntero a los indicadores que se utilizan para la asignación.</span><span class="sxs-lookup"><span data-stu-id="6c459-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="6c459-108">Este valor es una máscara de bits de la [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="6c459-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="6c459-109">[out] El nombre de la DLL no administrada de destino.</span><span class="sxs-lookup"><span data-stu-id="6c459-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="6c459-110">[in] El tamaño en caracteres anchos de `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="6c459-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="6c459-111">[out] El número de caracteres anchos devueltos en `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="6c459-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="6c459-112">[out] Un puntero a un símbolo (token) de ModuleRef que representa la biblioteca de objetos de destino no administrada.</span><span class="sxs-lookup"><span data-stu-id="6c459-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c459-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c459-113">Requirements</span></span>  
 <span data-ttu-id="6c459-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c459-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c459-115">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6c459-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6c459-116">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c459-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6c459-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c459-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c459-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c459-118">See Also</span></span>  
 [<span data-ttu-id="6c459-119">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c459-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="6c459-120">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c459-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
