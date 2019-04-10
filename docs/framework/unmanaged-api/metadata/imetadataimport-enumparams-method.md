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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221406"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="e6658-102">IMetaDataImport::EnumParams (Método)</span><span class="sxs-lookup"><span data-stu-id="e6658-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="e6658-103">Enumera los tokens de ParamDef que representan los parámetros del método al que hace referencia el token de MethodDef especificado.</span><span class="sxs-lookup"><span data-stu-id="e6658-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6658-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6658-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6658-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6658-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e6658-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="e6658-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="e6658-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="e6658-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="e6658-108">[in] Un token de MethodDef que representa el método con los parámetros para enumerar.</span><span class="sxs-lookup"><span data-stu-id="e6658-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="e6658-109">[out] Matriz utilizada para almacenar los tokens de ParamDef.</span><span class="sxs-lookup"><span data-stu-id="e6658-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e6658-110">[in] Tamaño máximo de la matriz `rParams`.</span><span class="sxs-lookup"><span data-stu-id="e6658-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e6658-111">[out] El número de tokens de ParamDef devueltos en `rParams`.</span><span class="sxs-lookup"><span data-stu-id="e6658-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6658-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e6658-112">Return Value</span></span>  
  
|<span data-ttu-id="e6658-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6658-113">HRESULT</span></span>|<span data-ttu-id="e6658-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6658-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumParams` <span data-ttu-id="e6658-115">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e6658-115">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e6658-116">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="e6658-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="e6658-117">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="e6658-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6658-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6658-118">Requirements</span></span>  
 <span data-ttu-id="e6658-119">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6658-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6658-120">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="e6658-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e6658-121">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e6658-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e6658-122">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e6658-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e6658-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6658-123">See also</span></span>

- [<span data-ttu-id="e6658-124">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6658-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e6658-125">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6658-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
