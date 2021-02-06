---
description: 'Más información sobre: IMetaDataEmit:: SetFieldProps ((método)'
title: IMetaDataEmit::SetFieldProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
ms.openlocfilehash: ee9964077e556a1d0666a836ca0c3bab92540252
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658014"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="d2c44-103">IMetaDataEmit::SetFieldProps (Método)</span><span class="sxs-lookup"><span data-stu-id="d2c44-103">IMetaDataEmit::SetFieldProps Method</span></span>

<span data-ttu-id="d2c44-104">Establece o actualiza el valor predeterminado para el campo al que hace referencia el token de campo especificado.</span><span class="sxs-lookup"><span data-stu-id="d2c44-104">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2c44-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2c44-105">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2c44-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d2c44-106">Parameters</span></span>  

 `fd`  
 <span data-ttu-id="d2c44-107">de El token para el campo de destino.</span><span class="sxs-lookup"><span data-stu-id="d2c44-107">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="d2c44-108">de Atributos de campo.</span><span class="sxs-lookup"><span data-stu-id="d2c44-108">[in] Field attributes.</span></span> <span data-ttu-id="d2c44-109">Se trata de una máscara de máscara de `CorFieldAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="d2c44-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="d2c44-110">de `ELEMENT_TYPE_` *\** Para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="d2c44-110">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="d2c44-111">Este es un `CorElementType` valor.</span><span class="sxs-lookup"><span data-stu-id="d2c44-111">This is a `CorElementType` value.</span></span> <span data-ttu-id="d2c44-112">Si no se define una constante, establezca este valor en `ELEMENT_TYPE_END` .</span><span class="sxs-lookup"><span data-stu-id="d2c44-112">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="d2c44-113">de Valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="d2c44-113">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="d2c44-114">de Tamaño, en caracteres Unicode, de `pValue` .</span><span class="sxs-lookup"><span data-stu-id="d2c44-114">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2c44-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2c44-115">Requirements</span></span>  

 <span data-ttu-id="d2c44-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2c44-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2c44-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d2c44-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2c44-118">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2c44-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2c44-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2c44-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2c44-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2c44-120">See also</span></span>

- [<span data-ttu-id="d2c44-121">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2c44-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="d2c44-122">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2c44-122">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
