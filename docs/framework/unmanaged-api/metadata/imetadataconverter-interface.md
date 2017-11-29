---
title: IMetaDataConverter (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataConverter
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataConverter
helpviewer_keywords: IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f551a774a860f595cc90a7cca9eee2c726ef50ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="0b5f5-102">IMetaDataConverter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b5f5-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="0b5f5-103">Proporciona métodos para asignar las bibliotecas de tipos a sus firmas de metadatos y para convertirlas de uno a otro.</span><span class="sxs-lookup"><span data-stu-id="0b5f5-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b5f5-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0b5f5-104">Methods</span></span>  
  
|<span data-ttu-id="0b5f5-105">Método</span><span class="sxs-lookup"><span data-stu-id="0b5f5-105">Method</span></span>|<span data-ttu-id="0b5f5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b5f5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b5f5-107">GetMetaDataFromTypeInfo (método)</span><span class="sxs-lookup"><span data-stu-id="0b5f5-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="0b5f5-108">Obtiene un puntero a un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instancia que representa la firma de metadatos de la biblioteca de tipos al que hace referencia especificado `ITypeInfo` instancia.</span><span class="sxs-lookup"><span data-stu-id="0b5f5-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="0b5f5-109">GetMetaDataFromTypeLib (método)</span><span class="sxs-lookup"><span data-stu-id="0b5f5-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="0b5f5-110">Obtiene un puntero a un `IMetaDataImport` instancia que representa la firma de metadatos de la biblioteca de tipo representada por el `ITypeLib` instancia.</span><span class="sxs-lookup"><span data-stu-id="0b5f5-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="0b5f5-111">GetTypeLibFromMetaData (método)</span><span class="sxs-lookup"><span data-stu-id="0b5f5-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="0b5f5-112">Obtiene un puntero a un `ITypeLib` instancia que representa la biblioteca de tipos que tiene los nombres de módulo y biblioteca especificados.</span><span class="sxs-lookup"><span data-stu-id="0b5f5-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b5f5-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b5f5-113">Requirements</span></span>  
 <span data-ttu-id="0b5f5-114">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b5f5-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b5f5-115">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0b5f5-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0b5f5-116">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b5f5-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0b5f5-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b5f5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b5f5-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b5f5-118">See Also</span></span>  
 [<span data-ttu-id="0b5f5-119">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="0b5f5-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="0b5f5-120">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b5f5-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
