---
title: IMetaDataImport::GetParamProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ed9bae4fde96f0878e40ed73b81cc8776571ada5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468063"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="f9619-102">IMetaDataImport::GetParamProps (Método)</span><span class="sxs-lookup"><span data-stu-id="f9619-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="f9619-103">Obtiene los valores de los metadatos del parámetro al que hace referencia el token de ParamDef especificado.</span><span class="sxs-lookup"><span data-stu-id="f9619-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9619-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9619-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f9619-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f9619-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f9619-106">[in] Un token de ParamDef que representa el parámetro para devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="f9619-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="f9619-107">[out] Un puntero a un token de MethodDef que representa el método que toma el parámetro.</span><span class="sxs-lookup"><span data-stu-id="f9619-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="f9619-108">[out] La posición ordinal del parámetro en la lista de argumentos de método.</span><span class="sxs-lookup"><span data-stu-id="f9619-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="f9619-109">[out] Un búfer para almacenar el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="f9619-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="f9619-110">[in] El tamaño solicitado en caracteres anchos de `szName`.</span><span class="sxs-lookup"><span data-stu-id="f9619-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="f9619-111">[out] El tamaño devuelto en caracteres anchos de `szName`.</span><span class="sxs-lookup"><span data-stu-id="f9619-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="f9619-112">[out] Un puntero a cualquier indicador de atributo asociado al parámetro.</span><span class="sxs-lookup"><span data-stu-id="f9619-112">[out] A pointer to any attribute flags associated with the parameter.</span></span> <span data-ttu-id="f9619-113">Se trata de una máscara de bits de `CorParamAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="f9619-113">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="f9619-114">[out] Un puntero a una marca que especifica que el parámetro es un <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="f9619-114">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f9619-115">[out] Un puntero a una cadena constante devuelta por el parámetro.</span><span class="sxs-lookup"><span data-stu-id="f9619-115">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="f9619-116">[out] El tamaño de `ppValue` en caracteres anchos, o cero si `ppValue` no contiene una cadena.</span><span class="sxs-lookup"><span data-stu-id="f9619-116">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9619-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f9619-117">Remarks</span></span>

<span data-ttu-id="f9619-118">Los valores de secuencia en `pulSequence` comienzan por 1 para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="f9619-118">The sequence values in `pulSequence` begin with 1 for parameters.</span></span> <span data-ttu-id="f9619-119">Un valor devuelto tiene un número de secuencia de 0.</span><span class="sxs-lookup"><span data-stu-id="f9619-119">A return value has a sequence number of 0.</span></span>

## <a name="requirements"></a><span data-ttu-id="f9619-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f9619-120">Requirements</span></span>  
 <span data-ttu-id="f9619-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9619-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9619-122">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="f9619-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f9619-123">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f9619-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f9619-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9619-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9619-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9619-125">See also</span></span>
- [<span data-ttu-id="f9619-126">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9619-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f9619-127">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9619-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
