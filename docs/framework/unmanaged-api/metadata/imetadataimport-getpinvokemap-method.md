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
ms.openlocfilehash: c458fef77b49f522ca21dd5487731f4d43588cea
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437099"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="ef834-102">IMetaDataImport::GetPinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="ef834-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="ef834-103">Obtiene un token ModuleRef para representar el ensamblado de destino de una llamada PInvoke.</span><span class="sxs-lookup"><span data-stu-id="ef834-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef834-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef834-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef834-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef834-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ef834-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span><span class="sxs-lookup"><span data-stu-id="ef834-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="ef834-107">[out] A pointer to flags used for mapping.</span><span class="sxs-lookup"><span data-stu-id="ef834-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="ef834-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span><span class="sxs-lookup"><span data-stu-id="ef834-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="ef834-109">[out] The name of the unmanaged target DLL.</span><span class="sxs-lookup"><span data-stu-id="ef834-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="ef834-110">[in] The size in wide characters of `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="ef834-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="ef834-111">[out] The number of wide characters returned in `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="ef834-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="ef834-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span><span class="sxs-lookup"><span data-stu-id="ef834-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef834-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef834-113">Requirements</span></span>  
 <span data-ttu-id="ef834-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef834-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef834-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ef834-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ef834-116">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef834-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ef834-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef834-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef834-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef834-118">See also</span></span>

- [<span data-ttu-id="ef834-119">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef834-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ef834-120">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef834-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
