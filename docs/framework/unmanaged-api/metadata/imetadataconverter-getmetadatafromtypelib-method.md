---
title: IMetaDataConverter::GetMetaDataFromTypeLib (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeLib
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib
helpviewer_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib method [.NET Framework metadata]
- GetMetaDataFromTypeLib method [.NET Framework metadata]
ms.assetid: 97dc3a56-adfa-431f-889e-06a35ac84d51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a390187e5fd73824f2fad026365371642235a6f9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777869"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="4b1c9-102">IMetaDataConverter::GetMetaDataFromTypeLib (Método)</span><span class="sxs-lookup"><span data-stu-id="4b1c9-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="4b1c9-103">Obtiene un puntero de interfaz a un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instancia que representa la firma de metadatos de la biblioteca de tipos representada por el `ITypeLib` instancia.</span><span class="sxs-lookup"><span data-stu-id="4b1c9-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b1c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b1c9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,   
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b1c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4b1c9-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="4b1c9-106">[in] Puntero a un `ITypeLib` objeto que representa la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="4b1c9-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="4b1c9-107">[out] Puntero a una ubicación que recibe la dirección de la `IMetaDataImport` instancia que representa la firma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="4b1c9-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b1c9-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b1c9-108">Requirements</span></span>  
 <span data-ttu-id="4b1c9-109">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b1c9-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b1c9-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="4b1c9-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b1c9-111">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4b1c9-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4b1c9-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b1c9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b1c9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b1c9-113">See also</span></span>

- [<span data-ttu-id="4b1c9-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b1c9-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4b1c9-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b1c9-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
