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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd138d0418bb9667a86419d719bf0b95a4bb1b12
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777118"
---
# <a name="importfileex-method"></a><span data-ttu-id="43244-102">ImportFileEx (Método)</span><span class="sxs-lookup"><span data-stu-id="43244-102">ImportFileEx Method</span></span>
<span data-ttu-id="43244-103">Importa el ensamblado indicado o el módulo sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="43244-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43244-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43244-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="43244-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43244-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="43244-106">Nombre completo del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="43244-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="43244-107">Nombre opcional del archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="43244-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="43244-108">Si es TRUE, se usa ImportTypes (; de lo contrario, la importación se debe realizar manualmente.</span><span class="sxs-lookup"><span data-stu-id="43244-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="43244-109">Marcas que se van a pasar al [método OpenScope](../metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="43244-109">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="43244-110">Recibe el identificador del archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="43244-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="43244-111">Recibe la interfaz de [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) de ámbito de importación de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="43244-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="43244-112">Se establece en NULL si el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="43244-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="43244-113">Recibe el recuento de archivos y/o ámbitos importados.</span><span class="sxs-lookup"><span data-stu-id="43244-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43244-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="43244-114">Return Value</span></span>  
 <span data-ttu-id="43244-115">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="43244-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43244-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43244-116">Requirements</span></span>  
 <span data-ttu-id="43244-117">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="43244-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43244-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="43244-118">See also</span></span>

- [<span data-ttu-id="43244-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43244-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="43244-120">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43244-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="43244-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="43244-121">ALink API</span></span>](index.md)
