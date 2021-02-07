---
description: 'Más información sobre: IMetaDataImport:: EnumParams ((método)'
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
ms.openlocfilehash: 3402e0277631cb54232269ad96194583cc466c4d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688811"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="70773-103">IMetaDataImport::EnumParams (Método)</span><span class="sxs-lookup"><span data-stu-id="70773-103">IMetaDataImport::EnumParams Method</span></span>

<span data-ttu-id="70773-104">Enumera los tokens de ParamDef que representan los parámetros del método al que hace referencia el token de MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="70773-104">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70773-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70773-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70773-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70773-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="70773-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="70773-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="70773-108">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="70773-108">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="70773-109">de Símbolo (token) de MethodDef que representa el método con los parámetros que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="70773-109">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="70773-110">enuncia Matriz utilizada para almacenar los tokens de ParamDef.</span><span class="sxs-lookup"><span data-stu-id="70773-110">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="70773-111">[in] Tamaño máximo de la matriz `rParams`.</span><span class="sxs-lookup"><span data-stu-id="70773-111">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="70773-112">enuncia Número de tokens de ParamDef devueltos en `rParams` .</span><span class="sxs-lookup"><span data-stu-id="70773-112">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70773-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="70773-113">Return Value</span></span>  
  
|<span data-ttu-id="70773-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="70773-114">HRESULT</span></span>|<span data-ttu-id="70773-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="70773-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="70773-116">`EnumParams` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="70773-116">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="70773-117">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="70773-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="70773-118">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="70773-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="70773-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70773-119">Requirements</span></span>  

 <span data-ttu-id="70773-120">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70773-120">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70773-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="70773-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="70773-122">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="70773-122">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="70773-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70773-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70773-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="70773-124">See also</span></span>

- [<span data-ttu-id="70773-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="70773-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="70773-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="70773-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
