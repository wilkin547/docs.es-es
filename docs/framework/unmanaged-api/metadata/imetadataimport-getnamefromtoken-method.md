---
title: "IMetaDataImport::GetNameFromToken (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: baa0c0e78f7912561b432effd2bf5503e0f06ae7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="e03dc-102">IMetaDataImport::GetNameFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="e03dc-102">IMetaDataImport::GetNameFromToken Method</span></span>
<span data-ttu-id="e03dc-103">Obtiene el nombre en UTF-8 del objeto al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="e03dc-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="e03dc-104">Este método está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="e03dc-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e03dc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e03dc-105">Syntax</span></span>  
  
```  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e03dc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e03dc-106">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e03dc-107">[in] El token que representa el objeto que se va a devolver el nombre de.</span><span class="sxs-lookup"><span data-stu-id="e03dc-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="e03dc-108">[out] Un puntero al nombre del objeto de UTF-8 en el montón.</span><span class="sxs-lookup"><span data-stu-id="e03dc-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e03dc-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e03dc-109">Remarks</span></span>  
 <span data-ttu-id="e03dc-110">`GetNameFromToken` está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="e03dc-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="e03dc-111">Como alternativa, llame a un método para obtener las propiedades de ese tipo de token necesario, como concreto `GetFieldProps` para un campo o `GetMethodProps` para un método.</span><span class="sxs-lookup"><span data-stu-id="e03dc-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e03dc-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e03dc-112">Requirements</span></span>  
 <span data-ttu-id="e03dc-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e03dc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e03dc-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e03dc-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e03dc-115">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e03dc-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e03dc-116">**Versiones de .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="e03dc-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e03dc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e03dc-117">See Also</span></span>  
 [<span data-ttu-id="e03dc-118">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e03dc-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e03dc-119">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e03dc-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
