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
ms.openlocfilehash: 2bc2b983171dc41d5ac37eda0359f1aaee4ebd6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725760"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="4bea9-102">IMetaDataEmit::DefineField (Método)</span><span class="sxs-lookup"><span data-stu-id="4bea9-102">IMetaDataEmit::DefineField Method</span></span>

<span data-ttu-id="4bea9-103">Crea una definición para un campo con la firma de metadatos especificada y obtiene un token para esa definición de campo.</span><span class="sxs-lookup"><span data-stu-id="4bea9-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bea9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bea9-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4bea9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4bea9-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="4bea9-106">de `mdTypeDef` Token de la clase o interfaz envolvente.</span><span class="sxs-lookup"><span data-stu-id="4bea9-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="4bea9-107">de Nombre del campo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="4bea9-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="4bea9-108">de Atributos del campo.</span><span class="sxs-lookup"><span data-stu-id="4bea9-108">[in] The field attributes.</span></span> <span data-ttu-id="4bea9-109">Se trata de una máscara de máscara de `CorFieldAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="4bea9-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="4bea9-110">de La firma del campo como un BLOB.</span><span class="sxs-lookup"><span data-stu-id="4bea9-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="4bea9-111">de Recuento de bytes de `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="4bea9-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="4bea9-112">de `ELEMENT_TYPE_` *\** Para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="4bea9-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="4bea9-113">Este es un `CorElementType` valor.</span><span class="sxs-lookup"><span data-stu-id="4bea9-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="4bea9-114">Si no se define un valor constante para el campo, use `ELEMENT_TYPE_END` .</span><span class="sxs-lookup"><span data-stu-id="4bea9-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="4bea9-115">de Valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="4bea9-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="4bea9-116">de El tamaño en caracteres (Unicode) de `pValue` .</span><span class="sxs-lookup"><span data-stu-id="4bea9-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="4bea9-117">enuncia El `mdFieldDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="4bea9-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bea9-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4bea9-118">Requirements</span></span>  

 <span data-ttu-id="4bea9-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bea9-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bea9-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4bea9-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4bea9-121">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4bea9-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4bea9-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bea9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bea9-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4bea9-123">See also</span></span>

- [<span data-ttu-id="4bea9-124">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4bea9-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="4bea9-125">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4bea9-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
