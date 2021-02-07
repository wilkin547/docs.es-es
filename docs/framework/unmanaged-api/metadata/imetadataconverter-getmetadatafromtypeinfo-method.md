---
description: 'Más información sobre: IMetaDataConverter:: Getmetadatafromtypeinfo ((método)'
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
ms.openlocfilehash: 224be07463b19ed9e22bef1a9d454d91a8086304
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753632"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="e7b9c-103">IMetaDataConverter::GetMetaDataFromTypeInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="e7b9c-103">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>

<span data-ttu-id="e7b9c-104">Obtiene un puntero a una instancia de [IMetaDataImport](imetadataimport-interface.md) que representa la firma de metadatos de la biblioteca de tipos a la que hace referencia la instancia de especificada `ITypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="e7b9c-104">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7b9c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7b9c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7b9c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e7b9c-106">Parameters</span></span>  

 `pITI`  
 <span data-ttu-id="e7b9c-107">de Un puntero a un `ITypeInfo` objeto que hace referencia a la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="e7b9c-107">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="e7b9c-108">enuncia Puntero a una ubicación que recibe la dirección de la `IMetaDataImport` instancia de que representa la firma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="e7b9c-108">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7b9c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7b9c-109">Requirements</span></span>  

 <span data-ttu-id="e7b9c-110">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7b9c-110">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7b9c-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e7b9c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e7b9c-112">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e7b9c-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e7b9c-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7b9c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7b9c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7b9c-114">See also</span></span>

- [<span data-ttu-id="e7b9c-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7b9c-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="e7b9c-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7b9c-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
