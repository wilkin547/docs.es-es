---
title: IMetaDataImport::GetPropertyProps (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08bd5beeb9fab1cd5b703c3afc4e82aaf71dbbc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777565"
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="35382-102">IMetaDataImport::GetPropertyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="35382-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="35382-103">Obtiene los metadatos para la propiedad representada por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="35382-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35382-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35382-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="35382-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35382-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="35382-106">[in] Un token que representa la propiedad para devolver los metadatos.</span><span class="sxs-lookup"><span data-stu-id="35382-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="35382-107">[out] Un puntero al token de TypeDef que representa el tipo que implementa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="35382-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="35382-108">[out] Un búfer para almacenar el nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="35382-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="35382-109">[in] El tamaño en caracteres anchos de `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="35382-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="35382-110">[out] El número de caracteres anchos que se devuelven en `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="35382-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="35382-111">[out] Un puntero a cualquier indicador de atributo aplicado a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="35382-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="35382-112">Este valor es una máscara de bits desde el [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="35382-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="35382-113">[out] Un puntero a la firma de metadatos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="35382-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="35382-114">[out] El número de bytes devuelto en `ppvSig`.</span><span class="sxs-lookup"><span data-stu-id="35382-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="35382-115">[out] Una marca que especifica el tipo de la constante que es el valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="35382-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="35382-116">Este valor es de CorElementType (enumeración).</span><span class="sxs-lookup"><span data-stu-id="35382-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="35382-117">[out] Un puntero a los bytes que almacenar el valor predeterminado para esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="35382-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="35382-118">[out] El tamaño en caracteres anchos de `ppDefaultValue`si `pdwCPlusTypeFlag` es ELEMENT_TYPE_STRING; en caso contrario, este valor no es relevante.</span><span class="sxs-lookup"><span data-stu-id="35382-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="35382-119">En ese caso, la longitud de `ppDefaultValue` se deduce del tipo especificado por `pdwCPlusTypeFlag`.</span><span class="sxs-lookup"><span data-stu-id="35382-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="35382-120">[out] Un puntero al token de MethodDef que representa el método de descriptor de acceso set de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="35382-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="35382-121">[out] Un puntero al token de MethodDef que representa el método de descriptor de acceso get de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="35382-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="35382-122">[out] Una matriz de los tokens de MethodDef que representan otros métodos asociados a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="35382-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="35382-123">[in] Tamaño máximo de la matriz `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="35382-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="35382-124">Si no se proporciona una matriz lo suficientemente grande como para contener todos los métodos, se omiten sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="35382-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="35382-125">[out] El número de tokens de MethodDef devueltos en `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="35382-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35382-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35382-126">Requirements</span></span>  
 <span data-ttu-id="35382-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35382-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35382-128">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="35382-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35382-129">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35382-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="35382-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35382-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35382-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="35382-131">See also</span></span>

- [<span data-ttu-id="35382-132">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="35382-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="35382-133">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="35382-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
