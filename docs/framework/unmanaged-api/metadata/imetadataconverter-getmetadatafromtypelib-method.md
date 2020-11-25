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
ms.openlocfilehash: ed0902824bdbb4d057bf5a7920db4b1d18eb7347
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714671"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="361a8-102">IMetaDataConverter::GetMetaDataFromTypeLib (Método)</span><span class="sxs-lookup"><span data-stu-id="361a8-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>

<span data-ttu-id="361a8-103">Obtiene un puntero de interfaz a una instancia de [IMetaDataImport](imetadataimport-interface.md) que representa la firma de metadatos de la biblioteca de tipos representada por la instancia de especificada `ITypeLib` .</span><span class="sxs-lookup"><span data-stu-id="361a8-103">Gets an interface pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="361a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="361a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="361a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="361a8-105">Parameters</span></span>  

 `pITL`  
 <span data-ttu-id="361a8-106">de Puntero a un `ITypeLib` objeto que representa la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="361a8-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="361a8-107">enuncia Puntero a una ubicación que recibe la dirección de la `IMetaDataImport` instancia de que representa la firma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="361a8-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="361a8-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="361a8-108">Requirements</span></span>  

 <span data-ttu-id="361a8-109">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="361a8-109">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="361a8-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="361a8-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="361a8-111">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="361a8-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="361a8-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="361a8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="361a8-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="361a8-113">See also</span></span>

- [<span data-ttu-id="361a8-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="361a8-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="361a8-115">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="361a8-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
