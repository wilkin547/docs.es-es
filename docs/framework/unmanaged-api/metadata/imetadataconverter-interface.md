---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 29709a4297d53cc5e40daf732ac89751ead95152
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449046"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="40cd3-102">IMetaDataConverter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40cd3-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="40cd3-103">Proporciona métodos para asignar las bibliotecas de tipos a sus firmas de metadatos y para convertirlas de uno a otro.</span><span class="sxs-lookup"><span data-stu-id="40cd3-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40cd3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="40cd3-104">Methods</span></span>  
  
|<span data-ttu-id="40cd3-105">Método</span><span class="sxs-lookup"><span data-stu-id="40cd3-105">Method</span></span>|<span data-ttu-id="40cd3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="40cd3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40cd3-107">GetMetaDataFromTypeInfo (método)</span><span class="sxs-lookup"><span data-stu-id="40cd3-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="40cd3-108">Obtiene un puntero a un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instancia que representa la firma de metadatos de la biblioteca de tipos al que hace referencia especificado `ITypeInfo` instancia.</span><span class="sxs-lookup"><span data-stu-id="40cd3-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="40cd3-109">GetMetaDataFromTypeLib (método)</span><span class="sxs-lookup"><span data-stu-id="40cd3-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="40cd3-110">Obtiene un puntero a un `IMetaDataImport` instancia que representa la firma de metadatos de la biblioteca de tipo representada por el `ITypeLib` instancia.</span><span class="sxs-lookup"><span data-stu-id="40cd3-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="40cd3-111">GetTypeLibFromMetaData (método)</span><span class="sxs-lookup"><span data-stu-id="40cd3-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="40cd3-112">Obtiene un puntero a un `ITypeLib` instancia que representa la biblioteca de tipos que tiene los nombres de módulo y biblioteca especificados.</span><span class="sxs-lookup"><span data-stu-id="40cd3-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40cd3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40cd3-113">Requirements</span></span>  
 <span data-ttu-id="40cd3-114">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40cd3-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40cd3-115">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="40cd3-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="40cd3-116">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="40cd3-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="40cd3-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40cd3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40cd3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="40cd3-118">See Also</span></span>  
 [<span data-ttu-id="40cd3-119">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="40cd3-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="40cd3-120">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40cd3-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
