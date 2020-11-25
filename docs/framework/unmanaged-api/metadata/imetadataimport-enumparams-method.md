---
title: IMetaDataImport::EnumParams (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type:
- apiref
ms.openlocfilehash: b41f9bb05a43ac4c6dd8a89c45ef4826741e5679
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728269"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="bdfdd-102">IMetaDataImport::EnumParams (Método)</span><span class="sxs-lookup"><span data-stu-id="bdfdd-102">IMetaDataImport::EnumParams Method</span></span>

<span data-ttu-id="bdfdd-103">Enumera los tokens de ParamDef que representan los parámetros del método al que hace referencia el token de MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="bdfdd-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdfdd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bdfdd-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdfdd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bdfdd-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="bdfdd-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="bdfdd-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="bdfdd-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="bdfdd-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="bdfdd-108">de Símbolo (token) de MethodDef que representa el método con los parámetros que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="bdfdd-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="bdfdd-109">enuncia Matriz utilizada para almacenar los tokens de ParamDef.</span><span class="sxs-lookup"><span data-stu-id="bdfdd-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bdfdd-110">[in] Tamaño máximo de la matriz `rParams`.</span><span class="sxs-lookup"><span data-stu-id="bdfdd-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="bdfdd-111">enuncia Número de tokens de ParamDef devueltos en `rParams` .</span><span class="sxs-lookup"><span data-stu-id="bdfdd-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bdfdd-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bdfdd-112">Return Value</span></span>  
  
|<span data-ttu-id="bdfdd-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bdfdd-113">HRESULT</span></span>|<span data-ttu-id="bdfdd-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdfdd-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bdfdd-115">`EnumParams` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="bdfdd-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bdfdd-116">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="bdfdd-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="bdfdd-117">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="bdfdd-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bdfdd-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bdfdd-118">Requirements</span></span>  

 <span data-ttu-id="bdfdd-119">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdfdd-119">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdfdd-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bdfdd-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bdfdd-121">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bdfdd-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bdfdd-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdfdd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdfdd-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bdfdd-123">See also</span></span>

- [<span data-ttu-id="bdfdd-124">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bdfdd-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="bdfdd-125">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bdfdd-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
