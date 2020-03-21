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
ms.openlocfilehash: 5fc71bf240b89afadbf8f2ba10906322921bdda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175335"
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="c61c1-102">IMetaDataImport::GetPropertyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="c61c1-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="c61c1-103">Obtiene los metadatos de la propiedad representada por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="c61c1-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c61c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c61c1-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="c61c1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c61c1-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="c61c1-106">[en] Un token que representa la propiedad para la que se va a devolver metadatos.</span><span class="sxs-lookup"><span data-stu-id="c61c1-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="c61c1-107">[fuera] Puntero al token TypeDef que representa el tipo que implementa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c61c1-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="c61c1-108">[fuera] Un búfer para contener el nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="c61c1-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="c61c1-109">[en] El tamaño en `szProperty`caracteres anchos de .</span><span class="sxs-lookup"><span data-stu-id="c61c1-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="c61c1-110">[fuera] El número de caracteres anchos devueltos en `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="c61c1-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="c61c1-111">[fuera] Puntero a cualquier marca de atributo aplicada a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c61c1-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="c61c1-112">Este valor es una máscara de bits de la [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="c61c1-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="c61c1-113">[fuera] Un puntero a la firma de metadatos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c61c1-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="c61c1-114">[fuera] El número de `ppvSig`bytes devueltos en .</span><span class="sxs-lookup"><span data-stu-id="c61c1-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="c61c1-115">[fuera] Marca que especifica el tipo de la constante que es el valor predeterminado de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c61c1-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="c61c1-116">Este valor procede de la enumeración CorElementType.</span><span class="sxs-lookup"><span data-stu-id="c61c1-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="c61c1-117">[fuera] Puntero a los bytes que almacenan el valor predeterminado de esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="c61c1-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="c61c1-118">[fuera] El tamaño en `ppDefaultValue`caracteres `pdwCPlusTypeFlag` anchos de , if es ELEMENT_TYPE_STRING; de lo contrario, este valor no es relevante.</span><span class="sxs-lookup"><span data-stu-id="c61c1-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="c61c1-119">En ese caso, `ppDefaultValue` la longitud de se deduce del `pdwCPlusTypeFlag`tipo especificado por .</span><span class="sxs-lookup"><span data-stu-id="c61c1-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="c61c1-120">[fuera] Puntero al token MethodDef que representa el método de descriptor de acceso set para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c61c1-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="c61c1-121">[fuera] Puntero al token MethodDef que representa el método de descriptor de acceso get para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c61c1-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="c61c1-122">[fuera] Matriz de tokens MethodDef que representan otros métodos asociados a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c61c1-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c61c1-123">[in] Tamaño máximo de la matriz `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="c61c1-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="c61c1-124">Si no proporciona una matriz lo suficientemente grande como para contener todos los métodos, se omiten sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="c61c1-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="c61c1-125">[fuera] El número de tokens MethodDef devueltos en `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="c61c1-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c61c1-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c61c1-126">Requirements</span></span>  
 <span data-ttu-id="c61c1-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c61c1-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c61c1-128">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c61c1-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c61c1-129">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c61c1-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c61c1-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c61c1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c61c1-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c61c1-131">See also</span></span>

- [<span data-ttu-id="c61c1-132">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c61c1-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c61c1-133">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c61c1-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
