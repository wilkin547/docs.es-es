---
title: "IMetaDataImport::GetInterfaceImplProps (Método)"
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
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: afc73536f332bd24fadee33d6321a106ccd175f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="69d5a-102">IMetaDataImport::GetInterfaceImplProps (Método)</span><span class="sxs-lookup"><span data-stu-id="69d5a-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="69d5a-103">Obtiene un puntero a los tokens de metadatos para el <xref:System.Type> que implementa el método especificado, y para la interfaz que declara ese método.</span><span class="sxs-lookup"><span data-stu-id="69d5a-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69d5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69d5a-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69d5a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="69d5a-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="69d5a-106">[in] El token de metadatos que representa el método para devolver los tokens de clase y la interfaz de.</span><span class="sxs-lookup"><span data-stu-id="69d5a-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="69d5a-107">[out] El token de metadatos que representa la clase que implementa el método.</span><span class="sxs-lookup"><span data-stu-id="69d5a-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="69d5a-108">[out] El token de metadatos que representa la interfaz que define el método implementado.</span><span class="sxs-lookup"><span data-stu-id="69d5a-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69d5a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69d5a-109">Requirements</span></span>  
 <span data-ttu-id="69d5a-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69d5a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69d5a-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="69d5a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69d5a-112">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69d5a-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="69d5a-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69d5a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69d5a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="69d5a-114">See Also</span></span>  
 [<span data-ttu-id="69d5a-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69d5a-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="69d5a-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69d5a-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
