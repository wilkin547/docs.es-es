---
title: "IMetaDataImport::EnumInterfaceImpls (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumInterfaceImpls
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1d9f2883c32daafd8938bd1c80c035a3527cc6a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="b7295-102">IMetaDataImport::EnumInterfaceImpls (Método)</span><span class="sxs-lookup"><span data-stu-id="b7295-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="b7295-103">Enumera los tokens de MethodDef que representan implementaciones de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="b7295-103">Enumerates MethodDef tokens representing interface implementations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7295-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7295-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7295-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7295-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b7295-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="b7295-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="b7295-107">[in] El token de la definición de tipo cuyos símbolos (tokens) de MethodDef que representan implementaciones de interfaz es que hay que enumerar.</span><span class="sxs-lookup"><span data-stu-id="b7295-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="b7295-108">[out] Matriz utilizada para almacenar los tokens de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="b7295-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b7295-109">[in] Tamaño máximo de la matriz `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="b7295-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="b7295-110">[out] El número real de símbolos (tokens) devueltos en `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="b7295-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7295-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b7295-111">Return Value</span></span>  
  
|<span data-ttu-id="b7295-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b7295-112">HRESULT</span></span>|<span data-ttu-id="b7295-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7295-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b7295-114">`EnumInterfaceImpls`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b7295-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b7295-115">No hay ningún tokens de MethodDef para enumerar.</span><span class="sxs-lookup"><span data-stu-id="b7295-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="b7295-116">En ese caso, `pcImpls` se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="b7295-116">In that case, `pcImpls` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b7295-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7295-117">Requirements</span></span>  
 <span data-ttu-id="b7295-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7295-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7295-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b7295-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b7295-120">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7295-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b7295-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7295-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7295-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7295-122">See Also</span></span>  
 [<span data-ttu-id="b7295-123">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7295-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="b7295-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7295-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
