---
title: IMetaDataImport::GetInterfaceImplProps (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91cb42a5bf1115de82b5fe28693cb77b66915c9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600563"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="5f5b2-102">IMetaDataImport::GetInterfaceImplProps (Método)</span><span class="sxs-lookup"><span data-stu-id="5f5b2-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="5f5b2-103">Obtiene un puntero a los tokens de metadatos para el <xref:System.Type> que implementa el método especificado, y para la interfaz que declara ese método.</span><span class="sxs-lookup"><span data-stu-id="5f5b2-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f5b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f5b2-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f5b2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f5b2-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="5f5b2-106">[in] El token de metadatos que representa el método para devolver los tokens de clase y la interfaz de.</span><span class="sxs-lookup"><span data-stu-id="5f5b2-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="5f5b2-107">[out] El token de metadatos que representa la clase que implementa el método.</span><span class="sxs-lookup"><span data-stu-id="5f5b2-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="5f5b2-108">[out] El token de metadatos que representa la interfaz que define el método implementado.</span><span class="sxs-lookup"><span data-stu-id="5f5b2-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f5b2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f5b2-109">Requirements</span></span>  
 <span data-ttu-id="5f5b2-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f5b2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f5b2-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="5f5b2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f5b2-112">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5f5b2-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f5b2-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f5b2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f5b2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f5b2-114">See also</span></span>
- [<span data-ttu-id="5f5b2-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f5b2-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5f5b2-116">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f5b2-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
