---
description: 'Más información acerca de: interfaz IMetaDataConverter'
title: IMetaDataConverter (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
ms.openlocfilehash: 6ed84083bad924e760c576afe485bd7ccad012cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789260"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="f4989-103">IMetaDataConverter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4989-103">IMetaDataConverter Interface</span></span>

<span data-ttu-id="f4989-104">Proporciona métodos para asignar las bibliotecas de tipos a sus firmas de metadatos y para convertirlas de uno a otro.</span><span class="sxs-lookup"><span data-stu-id="f4989-104">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4989-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f4989-105">Methods</span></span>  
  
|<span data-ttu-id="f4989-106">Método</span><span class="sxs-lookup"><span data-stu-id="f4989-106">Method</span></span>|<span data-ttu-id="f4989-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4989-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4989-108">Método GetMetaDataFromTypeInfo</span><span class="sxs-lookup"><span data-stu-id="f4989-108">GetMetaDataFromTypeInfo Method</span></span>](imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="f4989-109">Obtiene un puntero a una instancia de [IMetaDataImport](imetadataimport-interface.md) que representa la firma de metadatos para la biblioteca de tipos a la que hace referencia la instancia de especificada `ITypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="f4989-109">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="f4989-110">Método GetMetaDataFromTypeLib</span><span class="sxs-lookup"><span data-stu-id="f4989-110">GetMetaDataFromTypeLib Method</span></span>](imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="f4989-111">Obtiene un puntero a una `IMetaDataImport` instancia de que representa la firma de metadatos para la biblioteca de tipos representada por la instancia de especificada `ITypeLib` .</span><span class="sxs-lookup"><span data-stu-id="f4989-111">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="f4989-112">Método GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="f4989-112">GetTypeLibFromMetaData Method</span></span>](imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="f4989-113">Obtiene un puntero a una `ITypeLib` instancia de que representa la biblioteca de tipos que tiene los nombres de módulo y de biblioteca especificados.</span><span class="sxs-lookup"><span data-stu-id="f4989-113">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4989-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4989-114">Requirements</span></span>  

 <span data-ttu-id="f4989-115">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4989-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4989-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f4989-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f4989-117">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f4989-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f4989-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4989-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4989-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4989-119">See also</span></span>

- [<span data-ttu-id="f4989-120">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="f4989-120">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="f4989-121">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4989-121">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
