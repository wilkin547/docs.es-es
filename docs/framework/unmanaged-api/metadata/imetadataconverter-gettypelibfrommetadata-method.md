---
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
ms.openlocfilehash: 9da4e34fa948db2fc73cbde813bac9b3430605ca
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436253"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="ed183-102">IMetaDataConverter::GetTypeLibFromMetaData (Método)</span><span class="sxs-lookup"><span data-stu-id="ed183-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="ed183-103">Obtiene un puntero a una instancia de `ITypeLib` que representa la biblioteca de tipos que tiene los nombres de biblioteca y de módulo especificados.</span><span class="sxs-lookup"><span data-stu-id="ed183-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed183-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed183-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed183-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed183-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="ed183-106">de Nombre del módulo de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="ed183-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="ed183-107">de Nombre de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="ed183-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="ed183-108">enuncia Puntero a una ubicación que recibe la dirección de la instancia de `ITypeLib` que representa la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="ed183-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed183-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed183-109">Requirements</span></span>  
 <span data-ttu-id="ed183-110">**Plataforma:** Consulte [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed183-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed183-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ed183-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed183-112">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ed183-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed183-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed183-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed183-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed183-114">See also</span></span>

- [<span data-ttu-id="ed183-115">IMetaDataConverter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed183-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
