---
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
ms.openlocfilehash: 6b5e7bbe2303a200d7829fea12e228a513595f97
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716560"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="99611-102">IMetaDataImport::EnumUnresolvedMethods (Método)</span><span class="sxs-lookup"><span data-stu-id="99611-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>

<span data-ttu-id="99611-103">Enumera los tokens de MemberDef que representan los métodos no resueltos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="99611-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99611-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99611-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99611-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99611-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="99611-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="99611-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="99611-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="99611-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="99611-108">enuncia Matriz utilizada para almacenar los tokens de MemberDef.</span><span class="sxs-lookup"><span data-stu-id="99611-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="99611-109">[in] Tamaño máximo de la matriz `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="99611-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="99611-110">enuncia El número de tokens de MemberDef devueltos en `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="99611-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99611-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="99611-111">Return Value</span></span>  
  
|<span data-ttu-id="99611-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99611-112">HRESULT</span></span>|<span data-ttu-id="99611-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="99611-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="99611-114">`EnumUnresolvedMethods` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="99611-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="99611-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="99611-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="99611-116">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="99611-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99611-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99611-117">Remarks</span></span>  

 <span data-ttu-id="99611-118">Un método sin resolver es aquel que se ha declarado pero no se ha implementado.</span><span class="sxs-lookup"><span data-stu-id="99611-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="99611-119">Un método se incluye en la enumeración si el método está marcado `miForwardRef` y `mdPinvokeImpl` o `miRuntime` está establecido en cero.</span><span class="sxs-lookup"><span data-stu-id="99611-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="99611-120">En otras palabras, un método sin resolver es un método de clase que se marca `miForwardRef` pero que no se implementa en código no administrado (se alcanza a través de PInvoke) ni lo implementa internamente el propio Runtime.</span><span class="sxs-lookup"><span data-stu-id="99611-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="99611-121">La enumeración excluye todos los métodos que se definen en el ámbito del módulo (Globals) o en interfaces o clases abstractas.</span><span class="sxs-lookup"><span data-stu-id="99611-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99611-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99611-122">Requirements</span></span>  

 <span data-ttu-id="99611-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99611-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99611-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="99611-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99611-125">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99611-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99611-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99611-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99611-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99611-127">See also</span></span>

- [<span data-ttu-id="99611-128">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99611-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="99611-129">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99611-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
