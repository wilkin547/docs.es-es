---
description: 'Más información sobre: IMetaDataConverter:: Gettypelibfrommetadata ((método)'
title: IMetaDataConverter::GetTypeLibFromMetaData (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
ms.openlocfilehash: 5eecc87f938740366b7938d6ec3d1460ebcfb7eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789273"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="434b7-103">IMetaDataConverter::GetTypeLibFromMetaData (Método)</span><span class="sxs-lookup"><span data-stu-id="434b7-103">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>

<span data-ttu-id="434b7-104">Obtiene un puntero a una `ITypeLib` instancia de que representa la biblioteca de tipos que tiene los nombres de biblioteca y de módulo especificados.</span><span class="sxs-lookup"><span data-stu-id="434b7-104">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="434b7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="434b7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="434b7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="434b7-106">Parameters</span></span>  

 `strModule`  
 <span data-ttu-id="434b7-107">de Nombre del módulo de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="434b7-107">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="434b7-108">de Nombre de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="434b7-108">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="434b7-109">enuncia Puntero a una ubicación que recibe la dirección de la `ITypeLib` instancia de que representa la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="434b7-109">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="434b7-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="434b7-110">Requirements</span></span>  

 <span data-ttu-id="434b7-111">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="434b7-111">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="434b7-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="434b7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="434b7-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="434b7-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="434b7-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="434b7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="434b7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="434b7-115">See also</span></span>

- [<span data-ttu-id="434b7-116">IMetaDataConverter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="434b7-116">IMetaDataConverter Interface</span></span>](imetadataconverter-interface.md)
