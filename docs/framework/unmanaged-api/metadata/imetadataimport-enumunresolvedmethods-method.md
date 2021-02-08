---
description: 'Más información sobre: IMetaDataImport:: EnumUnresolvedMethods ((método)'
title: IMetaDataImport::EnumUnresolvedMethods (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
ms.openlocfilehash: e894ecdde91a2263783234d73fa50d890a13e413
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799335"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="f2911-103">IMetaDataImport::EnumUnresolvedMethods (Método)</span><span class="sxs-lookup"><span data-stu-id="f2911-103">IMetaDataImport::EnumUnresolvedMethods Method</span></span>

<span data-ttu-id="f2911-104">Enumera los tokens de MemberDef que representan los métodos no resueltos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="f2911-104">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2911-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2911-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2911-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2911-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="f2911-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="f2911-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f2911-108">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="f2911-108">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="f2911-109">enuncia Matriz utilizada para almacenar los tokens de MemberDef.</span><span class="sxs-lookup"><span data-stu-id="f2911-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f2911-110">[in] Tamaño máximo de la matriz `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="f2911-110">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f2911-111">enuncia El número de tokens de MemberDef devueltos en `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="f2911-111">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2911-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f2911-112">Return Value</span></span>  
  
|<span data-ttu-id="f2911-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2911-113">HRESULT</span></span>|<span data-ttu-id="f2911-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2911-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f2911-115">`EnumUnresolvedMethods` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f2911-115">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f2911-116">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="f2911-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="f2911-117">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="f2911-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2911-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f2911-118">Remarks</span></span>  

 <span data-ttu-id="f2911-119">Un método sin resolver es aquel que se ha declarado pero no se ha implementado.</span><span class="sxs-lookup"><span data-stu-id="f2911-119">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="f2911-120">Un método se incluye en la enumeración si el método está marcado `miForwardRef` y `mdPinvokeImpl` o `miRuntime` está establecido en cero.</span><span class="sxs-lookup"><span data-stu-id="f2911-120">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="f2911-121">En otras palabras, un método sin resolver es un método de clase que se marca `miForwardRef` pero que no se implementa en código no administrado (se alcanza a través de PInvoke) ni lo implementa internamente el propio Runtime.</span><span class="sxs-lookup"><span data-stu-id="f2911-121">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="f2911-122">La enumeración excluye todos los métodos que se definen en el ámbito del módulo (Globals) o en interfaces o clases abstractas.</span><span class="sxs-lookup"><span data-stu-id="f2911-122">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2911-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2911-123">Requirements</span></span>  

 <span data-ttu-id="f2911-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2911-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2911-125">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f2911-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2911-126">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2911-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f2911-127">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2911-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2911-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2911-128">See also</span></span>

- [<span data-ttu-id="f2911-129">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2911-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f2911-130">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2911-130">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
