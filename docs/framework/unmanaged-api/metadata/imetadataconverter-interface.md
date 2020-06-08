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
ms.openlocfilehash: 7a2a5080872f49a84e36c53ac337d91738c15e45
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501344"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="0ad82-102">IMetaDataConverter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ad82-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="0ad82-103">Proporciona métodos para asignar las bibliotecas de tipos a sus firmas de metadatos y para convertirlas de uno a otro.</span><span class="sxs-lookup"><span data-stu-id="0ad82-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ad82-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0ad82-104">Methods</span></span>  
  
|<span data-ttu-id="0ad82-105">Método</span><span class="sxs-lookup"><span data-stu-id="0ad82-105">Method</span></span>|<span data-ttu-id="0ad82-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ad82-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ad82-107">Método GetMetaDataFromTypeInfo</span><span class="sxs-lookup"><span data-stu-id="0ad82-107">GetMetaDataFromTypeInfo Method</span></span>](imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="0ad82-108">Obtiene un puntero a una instancia de [IMetaDataImport](imetadataimport-interface.md) que representa la firma de metadatos para la biblioteca de tipos a la que hace referencia la instancia de especificada `ITypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="0ad82-108">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="0ad82-109">Método GetMetaDataFromTypeLib</span><span class="sxs-lookup"><span data-stu-id="0ad82-109">GetMetaDataFromTypeLib Method</span></span>](imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="0ad82-110">Obtiene un puntero a una `IMetaDataImport` instancia de que representa la firma de metadatos para la biblioteca de tipos representada por la instancia de especificada `ITypeLib` .</span><span class="sxs-lookup"><span data-stu-id="0ad82-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="0ad82-111">Método GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="0ad82-111">GetTypeLibFromMetaData Method</span></span>](imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="0ad82-112">Obtiene un puntero a una `ITypeLib` instancia de que representa la biblioteca de tipos que tiene los nombres de módulo y de biblioteca especificados.</span><span class="sxs-lookup"><span data-stu-id="0ad82-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0ad82-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ad82-113">Requirements</span></span>  
 <span data-ttu-id="0ad82-114">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ad82-114">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ad82-115">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0ad82-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ad82-116">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0ad82-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0ad82-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ad82-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad82-118">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="0ad82-118">See also</span></span>

- [<span data-ttu-id="0ad82-119">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="0ad82-119">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="0ad82-120">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ad82-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
