---
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
ms.openlocfilehash: efc627619d9abf9cfa6010e1c0ca709989b9cad3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445455"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="cd2c4-102">IMetaDataEmit::SetFieldProps (Método)</span><span class="sxs-lookup"><span data-stu-id="cd2c4-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="cd2c4-103">Establece o actualiza el valor predeterminado para el campo al que hace referencia el token de campo especificado.</span><span class="sxs-lookup"><span data-stu-id="cd2c4-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd2c4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd2c4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd2c4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd2c4-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="cd2c4-106">de El token para el campo de destino.</span><span class="sxs-lookup"><span data-stu-id="cd2c4-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="cd2c4-107">de Atributos de campo.</span><span class="sxs-lookup"><span data-stu-id="cd2c4-107">[in] Field attributes.</span></span> <span data-ttu-id="cd2c4-108">Se trata de una máscara de máscara de valores `CorFieldAttr`.</span><span class="sxs-lookup"><span data-stu-id="cd2c4-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="cd2c4-109">de *\** de `ELEMENT_TYPE_`para el valor constante.</span><span class="sxs-lookup"><span data-stu-id="cd2c4-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="cd2c4-110">Se trata de un valor de `CorElementType`.</span><span class="sxs-lookup"><span data-stu-id="cd2c4-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="cd2c4-111">Si no se define una constante, establezca este valor en `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="cd2c4-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="cd2c4-112">de Valor constante para el campo.</span><span class="sxs-lookup"><span data-stu-id="cd2c4-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="cd2c4-113">de Tamaño, en caracteres Unicode, de `pValue`.</span><span class="sxs-lookup"><span data-stu-id="cd2c4-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd2c4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd2c4-114">Requirements</span></span>  
 <span data-ttu-id="cd2c4-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd2c4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd2c4-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cd2c4-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cd2c4-117">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cd2c4-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd2c4-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd2c4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd2c4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd2c4-119">See also</span></span>

- [<span data-ttu-id="cd2c4-120">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd2c4-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="cd2c4-121">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd2c4-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
