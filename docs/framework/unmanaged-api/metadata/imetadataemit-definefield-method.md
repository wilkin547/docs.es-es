---
title: IMetaDataEmit::DefineField (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: 8ca5ab70f60de4d783800fb18612a8f04cb9cee1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177714"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="f483b-102">IMetaDataEmit::DefineField (Método)</span><span class="sxs-lookup"><span data-stu-id="f483b-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="f483b-103">Crea una definición para un campo con la firma de metadatos especificada y obtiene un token a esa definición de campo.</span><span class="sxs-lookup"><span data-stu-id="f483b-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f483b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f483b-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineField (
    [in]  mdTypeDef   td,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwFieldFlags,
    [in]  PCCOR_SIGNATURE pvSigBlob,
    [in]  ULONG       cbSigBlob,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue,
    [out] mdFieldDef  *pmd
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f483b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f483b-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="f483b-106">[en] El `mdTypeDef` token para la clase o interfaz envolvente.</span><span class="sxs-lookup"><span data-stu-id="f483b-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="f483b-107">[en] El nombre del campo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="f483b-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="f483b-108">[en] Los atributos de campo.</span><span class="sxs-lookup"><span data-stu-id="f483b-108">[in] The field attributes.</span></span> <span data-ttu-id="f483b-109">Esta es una `CorFieldAttr` máscara de bits de valores.</span><span class="sxs-lookup"><span data-stu-id="f483b-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f483b-110">[en] La firma de campo como BLOB.</span><span class="sxs-lookup"><span data-stu-id="f483b-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="f483b-111">[en] El recuento de `pvSigBlob`bytes en .</span><span class="sxs-lookup"><span data-stu-id="f483b-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="f483b-112">[en] El `ELEMENT_TYPE_` *\** valor constante for.</span><span class="sxs-lookup"><span data-stu-id="f483b-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="f483b-113">Este es `CorElementType` un valor.</span><span class="sxs-lookup"><span data-stu-id="f483b-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="f483b-114">Si no define un valor constante `ELEMENT_TYPE_END`para el campo, utilice .</span><span class="sxs-lookup"><span data-stu-id="f483b-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="f483b-115">[en] El valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="f483b-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="f483b-116">[en] El tamaño en caracteres `pValue`(Unicode) de .</span><span class="sxs-lookup"><span data-stu-id="f483b-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="f483b-117">[fuera] El `mdFieldDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="f483b-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f483b-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f483b-118">Requirements</span></span>  
 <span data-ttu-id="f483b-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f483b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f483b-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f483b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f483b-121">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f483b-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f483b-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f483b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f483b-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f483b-123">See also</span></span>

- [<span data-ttu-id="f483b-124">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f483b-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f483b-125">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f483b-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
