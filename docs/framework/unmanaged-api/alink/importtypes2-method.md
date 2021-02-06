---
description: 'Más información sobre: método Importtypes2 ('
title: ImportTypes2 (Método)
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
ms.openlocfilehash: ca0d174061608f9b4abf524c43023e867e9a9646
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662616"
---
# <a name="importtypes2-method"></a><span data-ttu-id="35ae4-103">ImportTypes2 (Método)</span><span class="sxs-lookup"><span data-stu-id="35ae4-103">ImportTypes2 Method</span></span>

<span data-ttu-id="35ae4-104">Inicia la importación de tipos.</span><span class="sxs-lookup"><span data-stu-id="35ae4-104">Initiates the import of types.</span></span> <span data-ttu-id="35ae4-105">Llame a este método para empezar a importar los tipos de cada ámbito importado mediante el [método importFile](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="35ae4-105">Call this method to begin importing types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35ae4-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35ae4-106">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="35ae4-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35ae4-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="35ae4-108">IDENTIFICADOR del ensamblado en el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="35ae4-108">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="35ae4-109">IDENTIFICADOR del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="35ae4-109">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="35ae4-110">Ámbito de base cero desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="35ae4-110">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="35ae4-111">Recibe el identificador de enumerador para los tipos en el ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="35ae4-111">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="35ae4-112">Opcionalmente, recibe la interfaz de [interfaz IMetaDataImport2](../metadata/imetadataimport2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="35ae4-112">Optionally receives [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="35ae4-113">Opcionalmente, recibe el recuento de tipos en el ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="35ae4-113">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35ae4-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="35ae4-114">Return Value</span></span>  

 <span data-ttu-id="35ae4-115">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="35ae4-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35ae4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35ae4-116">Requirements</span></span>  

 <span data-ttu-id="35ae4-117">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="35ae4-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35ae4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="35ae4-118">See also</span></span>

- [<span data-ttu-id="35ae4-119">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="35ae4-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="35ae4-120">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="35ae4-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="35ae4-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="35ae4-121">ALink API</span></span>](index.md)
