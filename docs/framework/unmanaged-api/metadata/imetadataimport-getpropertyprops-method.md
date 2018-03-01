---
title: "IMetaDataImport::GetPropertyProps (Método)"
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
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d838f43b500ac3dd0c3b44d9d84dd9fc039c6e16
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="7aea4-102">IMetaDataImport::GetPropertyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="7aea4-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="7aea4-103">Obtiene los metadatos para la propiedad representada por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="7aea4-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aea4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7aea4-104">Syntax</span></span>  
  
```  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,   
   [out] LPCWSTR           szProperty,   
   [in]  ULONG             cchProperty,   
   [out] ULONG             *pchProperty,   
   [out] DWORD             *pdwPropFlags,   
   [out] PCCOR_SIGNATURE   *ppvSig,   
   [out] ULONG             *pbSig,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,   
   [out] mdMethodDef       *pmdGetter,   
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,   
   [out] ULONG             *pcOtherMethod   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7aea4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7aea4-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="7aea4-106">[in] Un token que representa la propiedad que se va a devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="7aea4-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="7aea4-107">[out] Un puntero al token de TypeDef que representa el tipo que implementa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7aea4-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="7aea4-108">[out] Un búfer para almacenar el nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="7aea4-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="7aea4-109">[in] El tamaño en caracteres anchos de `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="7aea4-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="7aea4-110">[out] El número de caracteres anchos devueltos en `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="7aea4-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="7aea4-111">[out] Puntero a cualquier indicador de atributo aplicado a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7aea4-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="7aea4-112">Este valor es una máscara de bits de la [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="7aea4-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="7aea4-113">[out] Un puntero a la firma de metadatos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7aea4-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="7aea4-114">[out] El número de bytes devueltos en `ppvSig`.</span><span class="sxs-lookup"><span data-stu-id="7aea4-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="7aea4-115">[out] Una marca que especifica el tipo de la constante que es el valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7aea4-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="7aea4-116">Este valor está entre el CorElementType (enumeración).</span><span class="sxs-lookup"><span data-stu-id="7aea4-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="7aea4-117">[out] Un puntero que indica los bytes que almacenan el valor predeterminado de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="7aea4-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="7aea4-118">[out] El tamaño en caracteres anchos de `ppDefaultValue`si `pdwCPlusTypeFlag` es ELEMENT_TYPE_STRING; en caso contrario, este valor no es relevante.</span><span class="sxs-lookup"><span data-stu-id="7aea4-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="7aea4-119">En ese caso, la longitud de `ppDefaultValue` se deduzcan del tipo especificado por `pdwCPlusTypeFlag`.</span><span class="sxs-lookup"><span data-stu-id="7aea4-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="7aea4-120">[out] Un puntero al token de MethodDef que representa el método de descriptor de acceso set para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7aea4-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="7aea4-121">[out] Un puntero al token de MethodDef que representa el método de descriptor de acceso get de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7aea4-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="7aea4-122">[out] Una matriz de los tokens de MethodDef que representan los otros métodos asociados a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="7aea4-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7aea4-123">[in] Tamaño máximo de la matriz `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="7aea4-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="7aea4-124">Si no se proporciona una matriz lo suficientemente grande como para contener todos los métodos, se omiten sin ninguna advertencia previa.</span><span class="sxs-lookup"><span data-stu-id="7aea4-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="7aea4-125">[out] El número de tokens de MethodDef devueltos en `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="7aea4-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aea4-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7aea4-126">Requirements</span></span>  
 <span data-ttu-id="7aea4-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7aea4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aea4-128">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7aea4-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7aea4-129">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7aea4-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7aea4-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7aea4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aea4-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="7aea4-131">See Also</span></span>  
 [<span data-ttu-id="7aea4-132">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7aea4-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="7aea4-133">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7aea4-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
