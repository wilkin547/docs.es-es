---
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
ms.openlocfilehash: 9e373f133830a5bc1f3cf7bdc8034cb67725d797
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705207"
---
# <a name="importfileex-method"></a><span data-ttu-id="11c7e-102">ImportFileEx (Método)</span><span class="sxs-lookup"><span data-stu-id="11c7e-102">ImportFileEx Method</span></span>

<span data-ttu-id="11c7e-103">Importa el ensamblado indicado o el módulo sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="11c7e-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11c7e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11c7e-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="11c7e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11c7e-105">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="11c7e-106">Nombre completo del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="11c7e-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="11c7e-107">Nombre opcional del archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="11c7e-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="11c7e-108">Si es TRUE, se usa ImportTypes (; de lo contrario, la importación se debe realizar manualmente.</span><span class="sxs-lookup"><span data-stu-id="11c7e-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="11c7e-109">Marcas que se van a pasar al [método OpenScope](../metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="11c7e-109">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="11c7e-110">Recibe el identificador del archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="11c7e-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="11c7e-111">Recibe la interfaz de [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) de ámbito de importación de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="11c7e-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="11c7e-112">Se establece en NULL si el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="11c7e-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="11c7e-113">Recibe el recuento de archivos y/o ámbitos importados.</span><span class="sxs-lookup"><span data-stu-id="11c7e-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11c7e-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="11c7e-114">Return Value</span></span>  

 <span data-ttu-id="11c7e-115">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="11c7e-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11c7e-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11c7e-116">Requirements</span></span>  

 <span data-ttu-id="11c7e-117">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="11c7e-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11c7e-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11c7e-118">See also</span></span>

- [<span data-ttu-id="11c7e-119">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="11c7e-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="11c7e-120">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="11c7e-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="11c7e-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="11c7e-121">ALink API</span></span>](index.md)
