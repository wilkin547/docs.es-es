---
description: 'Más información acerca de: IMetaDataEmit::D método efineField'
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
ms.openlocfilehash: 7636b1521de721cc183305e8a0763ff0a61f331b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753451"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="26c15-103">IMetaDataEmit::DefineField (Método)</span><span class="sxs-lookup"><span data-stu-id="26c15-103">IMetaDataEmit::DefineField Method</span></span>

<span data-ttu-id="26c15-104">Crea una definición para un campo con la firma de metadatos especificada y obtiene un token para esa definición de campo.</span><span class="sxs-lookup"><span data-stu-id="26c15-104">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26c15-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26c15-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="26c15-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="26c15-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="26c15-107">de `mdTypeDef` Token de la clase o interfaz envolvente.</span><span class="sxs-lookup"><span data-stu-id="26c15-107">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="26c15-108">de Nombre del campo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="26c15-108">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="26c15-109">de Atributos del campo.</span><span class="sxs-lookup"><span data-stu-id="26c15-109">[in] The field attributes.</span></span> <span data-ttu-id="26c15-110">Se trata de una máscara de máscara de `CorFieldAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="26c15-110">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="26c15-111">de La firma del campo como un BLOB.</span><span class="sxs-lookup"><span data-stu-id="26c15-111">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="26c15-112">de Recuento de bytes de `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="26c15-112">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="26c15-113">de `ELEMENT_TYPE_` *\** Para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="26c15-113">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="26c15-114">Este es un `CorElementType` valor.</span><span class="sxs-lookup"><span data-stu-id="26c15-114">This is a `CorElementType` value.</span></span> <span data-ttu-id="26c15-115">Si no se define un valor constante para el campo, use `ELEMENT_TYPE_END` .</span><span class="sxs-lookup"><span data-stu-id="26c15-115">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="26c15-116">de Valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="26c15-116">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="26c15-117">de El tamaño en caracteres (Unicode) de `pValue` .</span><span class="sxs-lookup"><span data-stu-id="26c15-117">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="26c15-118">enuncia El `mdFieldDef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="26c15-118">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26c15-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26c15-119">Requirements</span></span>  

 <span data-ttu-id="26c15-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26c15-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26c15-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="26c15-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="26c15-122">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="26c15-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26c15-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26c15-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c15-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="26c15-124">See also</span></span>

- [<span data-ttu-id="26c15-125">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="26c15-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="26c15-126">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="26c15-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
