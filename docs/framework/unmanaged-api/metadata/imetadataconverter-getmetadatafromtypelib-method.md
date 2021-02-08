---
description: 'Más información sobre: IMetaDataConverter:: GetMetaDataFromTypeLib ((método)'
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
ms.openlocfilehash: d1ed5feb9f42ea0f8dc802c4dad527be5d2ed25f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789286"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="7ce9b-103">IMetaDataConverter::GetMetaDataFromTypeLib (Método)</span><span class="sxs-lookup"><span data-stu-id="7ce9b-103">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>

<span data-ttu-id="7ce9b-104">Obtiene un puntero de interfaz a una instancia de [IMetaDataImport](imetadataimport-interface.md) que representa la firma de metadatos de la biblioteca de tipos representada por la instancia de especificada `ITypeLib` .</span><span class="sxs-lookup"><span data-stu-id="7ce9b-104">Gets an interface pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ce9b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ce9b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ce9b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ce9b-106">Parameters</span></span>  

 `pITL`  
 <span data-ttu-id="7ce9b-107">de Puntero a un `ITypeLib` objeto que representa la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="7ce9b-107">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="7ce9b-108">enuncia Puntero a una ubicación que recibe la dirección de la `IMetaDataImport` instancia de que representa la firma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="7ce9b-108">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ce9b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ce9b-109">Requirements</span></span>  

 <span data-ttu-id="7ce9b-110">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ce9b-110">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ce9b-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7ce9b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ce9b-112">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7ce9b-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7ce9b-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ce9b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ce9b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ce9b-114">See also</span></span>

- [<span data-ttu-id="7ce9b-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ce9b-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7ce9b-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ce9b-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
