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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e6e53f69f58c2f5778083d9b8f8be466b952cdd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090256"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="6a5f2-102">IMetaDataImport::EnumUnresolvedMethods (Método)</span><span class="sxs-lookup"><span data-stu-id="6a5f2-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="6a5f2-103">Enumera los tokens de MemberDef que representan los métodos no resueltos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="6a5f2-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a5f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a5f2-104">Syntax</span></span>  
  
```  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a5f2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6a5f2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6a5f2-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="6a5f2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="6a5f2-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="6a5f2-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="6a5f2-108">[out] Matriz utilizada para almacenar los tokens de MemberDef.</span><span class="sxs-lookup"><span data-stu-id="6a5f2-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6a5f2-109">[in] Tamaño máximo de la matriz `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="6a5f2-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="6a5f2-110">[out] El número de tokens de MemberDef devueltos en `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="6a5f2-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a5f2-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6a5f2-111">Return Value</span></span>  
  
|<span data-ttu-id="6a5f2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6a5f2-112">HRESULT</span></span>|<span data-ttu-id="6a5f2-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a5f2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumUnresolvedMethods` <span data-ttu-id="6a5f2-114">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6a5f2-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6a5f2-115">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="6a5f2-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="6a5f2-116">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="6a5f2-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a5f2-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6a5f2-117">Remarks</span></span>  
 <span data-ttu-id="6a5f2-118">Un método sin resolver es aquella que se ha declarado pero no implementado.</span><span class="sxs-lookup"><span data-stu-id="6a5f2-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="6a5f2-119">Un método se incluye en la enumeración si el método se marca `miForwardRef` y `mdPinvokeImpl` o `miRuntime` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="6a5f2-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="6a5f2-120">En otras palabras, un método sin resolver es un método de clase marcado `miForwardRef` pero que no se implementa en código no administrado (llegado a través de PInvoke) ni implementada internamente por el tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6a5f2-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="6a5f2-121">La enumeración excluye todos los métodos que se definen en el ámbito de módulo (globales) o en interfaces o clases abstractas.</span><span class="sxs-lookup"><span data-stu-id="6a5f2-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a5f2-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a5f2-122">Requirements</span></span>  
 <span data-ttu-id="6a5f2-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a5f2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a5f2-124">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="6a5f2-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a5f2-125">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6a5f2-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="6a5f2-126">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6a5f2-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6a5f2-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a5f2-127">See also</span></span>

- [<span data-ttu-id="6a5f2-128">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a5f2-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6a5f2-129">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a5f2-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
