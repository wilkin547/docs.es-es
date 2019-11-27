---
title: IMetaDataConverter::GetMetaDataFromTypeInfo (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeInfo
helpviewer_keywords:
- GetMetaDataFromTypeInfo method [.NET Framework metadata]
- IMetaDataConverter::GetMetaDataFromTypeInfo method [.NET Framework metadata]
ms.assetid: d44484bb-23a3-49c3-9e46-69d0d9ab4f0f
topic_type:
- apiref
ms.openlocfilehash: df7be11e8f275824fca658a9604178e7cf28e3ce
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436294"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="f7f8b-102">IMetaDataConverter::GetMetaDataFromTypeInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="f7f8b-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>
<span data-ttu-id="f7f8b-103">Obtiene un puntero a una instancia de [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) que representa la firma de metadatos de la biblioteca de tipos a la que hace referencia la instancia de `ITypeInfo` especificada.</span><span class="sxs-lookup"><span data-stu-id="f7f8b-103">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7f8b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7f8b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7f8b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7f8b-105">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="f7f8b-106">de Puntero a un objeto `ITypeInfo` que hace referencia a la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="f7f8b-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="f7f8b-107">enuncia Puntero a una ubicación que recibe la dirección de la instancia de `IMetaDataImport` que representa la firma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="f7f8b-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7f8b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7f8b-108">Requirements</span></span>  
 <span data-ttu-id="f7f8b-109">**Plataforma:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7f8b-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7f8b-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f7f8b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f7f8b-111">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f7f8b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f7f8b-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7f8b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f8b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7f8b-113">See also</span></span>

- [<span data-ttu-id="f7f8b-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7f8b-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f7f8b-115">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7f8b-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
