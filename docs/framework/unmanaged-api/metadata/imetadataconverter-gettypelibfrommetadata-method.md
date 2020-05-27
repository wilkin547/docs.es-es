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
ms.openlocfilehash: 79bd8901641ee587e94861c0aec85b812591ea48
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008422"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="62c77-102">IMetaDataConverter::GetTypeLibFromMetaData (Método)</span><span class="sxs-lookup"><span data-stu-id="62c77-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="62c77-103">Obtiene un puntero a una `ITypeLib` instancia de que representa la biblioteca de tipos que tiene los nombres de biblioteca y de módulo especificados.</span><span class="sxs-lookup"><span data-stu-id="62c77-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62c77-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62c77-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62c77-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62c77-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="62c77-106">de Nombre del módulo de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="62c77-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="62c77-107">de Nombre de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="62c77-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="62c77-108">enuncia Puntero a una ubicación que recibe la dirección de la `ITypeLib` instancia de que representa la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="62c77-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62c77-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62c77-109">Requirements</span></span>  
 <span data-ttu-id="62c77-110">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62c77-110">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62c77-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="62c77-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62c77-112">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62c77-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62c77-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62c77-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62c77-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62c77-114">See also</span></span>

- [<span data-ttu-id="62c77-115">IMetaDataConverter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62c77-115">IMetaDataConverter Interface</span></span>](imetadataconverter-interface.md)
