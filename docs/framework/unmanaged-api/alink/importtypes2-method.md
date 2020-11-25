---
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
ms.openlocfilehash: 2ec7708edd86b9f2656d0eee434992c3b73200ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705051"
---
# <a name="importtypes2-method"></a><span data-ttu-id="9b719-102">ImportTypes2 (Método)</span><span class="sxs-lookup"><span data-stu-id="9b719-102">ImportTypes2 Method</span></span>

<span data-ttu-id="9b719-103">Inicia la importación de tipos.</span><span class="sxs-lookup"><span data-stu-id="9b719-103">Initiates the import of types.</span></span> <span data-ttu-id="9b719-104">Llame a este método para empezar a importar los tipos de cada ámbito importado mediante el [método importFile](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="9b719-104">Call this method to begin importing types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b719-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b719-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="9b719-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9b719-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="9b719-107">IDENTIFICADOR del ensamblado en el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="9b719-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="9b719-108">IDENTIFICADOR del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="9b719-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="9b719-109">Ámbito de base cero desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="9b719-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="9b719-110">Recibe el identificador de enumerador para los tipos en el ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="9b719-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="9b719-111">Opcionalmente, recibe la interfaz de [interfaz IMetaDataImport2](../metadata/imetadataimport2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9b719-111">Optionally receives [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="9b719-112">Opcionalmente, recibe el recuento de tipos en el ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="9b719-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b719-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9b719-113">Return Value</span></span>  

 <span data-ttu-id="9b719-114">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="9b719-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b719-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b719-115">Requirements</span></span>  

 <span data-ttu-id="9b719-116">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="9b719-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b719-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9b719-117">See also</span></span>

- [<span data-ttu-id="9b719-118">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b719-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="9b719-119">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b719-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="9b719-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="9b719-120">ALink API</span></span>](index.md)
