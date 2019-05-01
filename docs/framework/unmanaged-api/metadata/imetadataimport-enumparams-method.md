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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ed5ddd74e61e63426871f659aa1c962d38fd534
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042601"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="8eba4-102">IMetaDataImport::EnumParams (Método)</span><span class="sxs-lookup"><span data-stu-id="8eba4-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="8eba4-103">Enumera los tokens de ParamDef que representan los parámetros del método al que hace referencia el token de MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="8eba4-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eba4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8eba4-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8eba4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8eba4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8eba4-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="8eba4-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="8eba4-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="8eba4-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="8eba4-108">[in] Un token de MethodDef que representa el método con los parámetros para enumerar.</span><span class="sxs-lookup"><span data-stu-id="8eba4-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="8eba4-109">[out] Matriz utilizada para almacenar los tokens de ParamDef.</span><span class="sxs-lookup"><span data-stu-id="8eba4-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8eba4-110">[in] Tamaño máximo de la matriz `rParams`.</span><span class="sxs-lookup"><span data-stu-id="8eba4-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8eba4-111">[out] El número de tokens de ParamDef devueltos en `rParams`.</span><span class="sxs-lookup"><span data-stu-id="8eba4-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8eba4-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8eba4-112">Return Value</span></span>  
  
|<span data-ttu-id="8eba4-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8eba4-113">HRESULT</span></span>|<span data-ttu-id="8eba4-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="8eba4-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8eba4-115">`EnumParams` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8eba4-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8eba4-116">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="8eba4-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="8eba4-117">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="8eba4-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8eba4-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8eba4-118">Requirements</span></span>  
 <span data-ttu-id="8eba4-119">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8eba4-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eba4-120">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="8eba4-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8eba4-121">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8eba4-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8eba4-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eba4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eba4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8eba4-123">See also</span></span>

- [<span data-ttu-id="8eba4-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8eba4-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8eba4-125">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8eba4-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
