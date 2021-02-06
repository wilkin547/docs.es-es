---
description: 'Más información sobre: método ImportTypes ('
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
ms.openlocfilehash: 9a30c735ca2c9ad0f945628c3de1eb1bb56efe2c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662629"
---
# <a name="importtypes-method"></a><span data-ttu-id="76e4a-103">ImportTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="76e4a-103">ImportTypes Method</span></span>

<span data-ttu-id="76e4a-104">Inicia la importación de tipos de cada ámbito importado mediante el [método importFile](importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="76e4a-104">Initiates the importing of types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76e4a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76e4a-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="76e4a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76e4a-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="76e4a-107">IDENTIFICADOR del ensamblado en el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="76e4a-107">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="76e4a-108">IDENTIFICADOR del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="76e4a-108">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="76e4a-109">Ámbito de base cero que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="76e4a-109">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="76e4a-110">Recibe el identificador de enumerador para los tipos de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="76e4a-110">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="76e4a-111">Opcionalmente, recibe la interfaz de [interfaz IMetaDataImport](../metadata/imetadataimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="76e4a-111">Optionally receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="76e4a-112">Opcionalmente, recibe el recuento de tipos en el ámbito indicado.</span><span class="sxs-lookup"><span data-stu-id="76e4a-112">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76e4a-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="76e4a-113">Return Value</span></span>  

 <span data-ttu-id="76e4a-114">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="76e4a-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76e4a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76e4a-115">Requirements</span></span>  

 <span data-ttu-id="76e4a-116">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="76e4a-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e4a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="76e4a-117">See also</span></span>

- [<span data-ttu-id="76e4a-118">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="76e4a-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="76e4a-119">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="76e4a-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="76e4a-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="76e4a-120">ALink API</span></span>](index.md)
