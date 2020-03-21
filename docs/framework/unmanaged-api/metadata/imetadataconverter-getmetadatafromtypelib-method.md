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
ms.openlocfilehash: 09a1605deda5b51be604c3b8f0c69fa5adcf9dc0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175959"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="f1cf1-102">IMetaDataConverter::GetMetaDataFromTypeLib (Método)</span><span class="sxs-lookup"><span data-stu-id="f1cf1-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="f1cf1-103">Obtiene un puntero de interfaz a un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instancia que representa la `ITypeLib` firma de metadatos de la biblioteca de tipos representada por la instancia especificada.</span><span class="sxs-lookup"><span data-stu-id="f1cf1-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1cf1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1cf1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1cf1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1cf1-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="f1cf1-106">[en] Puntero a `ITypeLib` un objeto que representa la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="f1cf1-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="f1cf1-107">[fuera] Puntero a una ubicación que recibe `IMetaDataImport` la dirección de la instancia que representa la firma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="f1cf1-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1cf1-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1cf1-108">Requirements</span></span>  
 <span data-ttu-id="f1cf1-109">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1cf1-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1cf1-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f1cf1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1cf1-111">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f1cf1-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f1cf1-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1cf1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1cf1-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1cf1-113">See also</span></span>

- [<span data-ttu-id="f1cf1-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1cf1-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f1cf1-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1cf1-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
