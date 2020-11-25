---
title: ImportTypes (Método)
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
ms.openlocfilehash: 762f78900add70238971978ceecda089d0c725ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705116"
---
# <a name="importtypes-method"></a><span data-ttu-id="76853-102">ImportTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="76853-102">ImportTypes Method</span></span>

<span data-ttu-id="76853-103">Inicia la importación de tipos de cada ámbito importado mediante el [método importFile](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="76853-103">Initiates the importing of types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76853-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76853-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="76853-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76853-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="76853-106">IDENTIFICADOR del ensamblado en el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="76853-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="76853-107">IDENTIFICADOR del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="76853-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="76853-108">Ámbito de base cero que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="76853-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="76853-109">Recibe el identificador de enumerador para los tipos de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="76853-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="76853-110">Opcionalmente, recibe la interfaz de [interfaz IMetaDataImport](../metadata/imetadataimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="76853-110">Optionally receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="76853-111">Opcionalmente, recibe el recuento de tipos en el ámbito indicado.</span><span class="sxs-lookup"><span data-stu-id="76853-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76853-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="76853-112">Return Value</span></span>  

 <span data-ttu-id="76853-113">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="76853-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76853-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76853-114">Requirements</span></span>  

 <span data-ttu-id="76853-115">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="76853-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76853-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="76853-116">See also</span></span>

- [<span data-ttu-id="76853-117">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="76853-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="76853-118">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="76853-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="76853-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="76853-119">ALink API</span></span>](index.md)
