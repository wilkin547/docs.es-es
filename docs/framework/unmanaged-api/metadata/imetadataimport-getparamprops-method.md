---
title: "IMetaDataImport::GetParamProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f393ccd6296cb06498b30a29c7ea55f088e0a393
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="62723-102">IMetaDataImport::GetParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="62723-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="62723-103">Obtiene los valores de los metadatos del parámetro al que hace referencia el token de ParamDef especificado.</span><span class="sxs-lookup"><span data-stu-id="62723-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62723-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62723-104">Syntax</span></span>  
  
```  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62723-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62723-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="62723-106">[in] Símbolo (token) de ParamDef que representa el parámetro para devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="62723-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="62723-107">[out] Un puntero a un símbolo (token) de MethodDef que representa el método que toma el parámetro.</span><span class="sxs-lookup"><span data-stu-id="62723-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="62723-108">[out] La posición ordinal del parámetro en la lista de argumentos de método.</span><span class="sxs-lookup"><span data-stu-id="62723-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="62723-109">[out] Un búfer para contener el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="62723-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="62723-110">[in] El tamaño solicitado en caracteres anchos de `szName`.</span><span class="sxs-lookup"><span data-stu-id="62723-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="62723-111">[out] El tamaño devuelto en caracteres anchos de `szName`.</span><span class="sxs-lookup"><span data-stu-id="62723-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="62723-112">[out] Puntero a cualquier indicador de atributo asociado al parámetro.</span><span class="sxs-lookup"><span data-stu-id="62723-112">[out] A pointer to any attribute flags associated with the parameter.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="62723-113">[out] Un puntero a una marca que especifica que el parámetro es un <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="62723-113">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="62723-114">[out] Un puntero a una cadena constante devuelta por el parámetro.</span><span class="sxs-lookup"><span data-stu-id="62723-114">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="62723-115">[out] El tamaño de `ppValue` en caracteres anchos, o cero si `ppValue` no contiene una cadena.</span><span class="sxs-lookup"><span data-stu-id="62723-115">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62723-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62723-116">Requirements</span></span>  
 <span data-ttu-id="62723-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62723-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62723-118">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="62723-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62723-119">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="62723-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62723-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62723-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62723-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="62723-121">See Also</span></span>  
 [<span data-ttu-id="62723-122">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="62723-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="62723-123">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="62723-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
