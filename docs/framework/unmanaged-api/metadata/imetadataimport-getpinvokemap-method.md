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
ms.openlocfilehash: 99aea385cf5e3c8bcf7cf39b7cc5618f99f8a631
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777590"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="9ec0a-102">IMetaDataImport::GetPinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="9ec0a-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="9ec0a-103">Obtiene un token ModuleRef para representar el ensamblado de destino de una llamada PInvoke.</span><span class="sxs-lookup"><span data-stu-id="9ec0a-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ec0a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ec0a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="9ec0a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9ec0a-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="9ec0a-106">[in] Un token de FieldDef o MethodDef para obtener los metadatos de asignación de PInvoke.</span><span class="sxs-lookup"><span data-stu-id="9ec0a-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="9ec0a-107">[out] Un puntero a los marcadores utilizados para la asignación.</span><span class="sxs-lookup"><span data-stu-id="9ec0a-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="9ec0a-108">Este valor es una máscara de bits desde el [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="9ec0a-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="9ec0a-109">[out] El nombre de la DLL de destino no administrado.</span><span class="sxs-lookup"><span data-stu-id="9ec0a-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="9ec0a-110">[in] El tamaño en caracteres anchos de `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="9ec0a-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="9ec0a-111">[out] El número de caracteres anchos que se devuelven en `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="9ec0a-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="9ec0a-112">[out] Un puntero a un token ModuleRef que representa la biblioteca de objetos de destino no administrado.</span><span class="sxs-lookup"><span data-stu-id="9ec0a-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ec0a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ec0a-113">Requirements</span></span>  
 <span data-ttu-id="9ec0a-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ec0a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ec0a-115">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="9ec0a-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9ec0a-116">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ec0a-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9ec0a-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ec0a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ec0a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ec0a-118">See also</span></span>

- [<span data-ttu-id="9ec0a-119">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ec0a-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9ec0a-120">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ec0a-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
