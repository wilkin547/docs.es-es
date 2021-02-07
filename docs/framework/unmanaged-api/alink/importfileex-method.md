---
description: 'Más información sobre: método Importfileex ('
title: ImportFileEx (Método)
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
ms.openlocfilehash: a8a7e5a142091bf7cc93f50a4ae20c59d800f3ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718023"
---
# <a name="importfileex-method"></a><span data-ttu-id="57c97-103">ImportFileEx (Método)</span><span class="sxs-lookup"><span data-stu-id="57c97-103">ImportFileEx Method</span></span>

<span data-ttu-id="57c97-104">Importa el ensamblado indicado o el módulo sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="57c97-104">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57c97-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57c97-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="57c97-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57c97-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="57c97-107">Nombre completo del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="57c97-107">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="57c97-108">Nombre opcional del archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="57c97-108">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="57c97-109">Si es TRUE, se usa ImportTypes (; de lo contrario, la importación se debe realizar manualmente.</span><span class="sxs-lookup"><span data-stu-id="57c97-109">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="57c97-110">Marcas que se van a pasar al [método OpenScope](../metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="57c97-110">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="57c97-111">Recibe el identificador del archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="57c97-111">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="57c97-112">Recibe la interfaz de [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) de ámbito de importación de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="57c97-112">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="57c97-113">Se establece en NULL si el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="57c97-113">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="57c97-114">Recibe el recuento de archivos y/o ámbitos importados.</span><span class="sxs-lookup"><span data-stu-id="57c97-114">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57c97-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="57c97-115">Return Value</span></span>  

 <span data-ttu-id="57c97-116">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="57c97-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57c97-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57c97-117">Requirements</span></span>  

 <span data-ttu-id="57c97-118">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="57c97-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57c97-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="57c97-119">See also</span></span>

- [<span data-ttu-id="57c97-120">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57c97-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="57c97-121">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57c97-121">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="57c97-122">API de ALink</span><span class="sxs-lookup"><span data-stu-id="57c97-122">ALink API</span></span>](index.md)
