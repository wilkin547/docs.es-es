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
ms.openlocfilehash: bee7db61beb9ed8c00cf584924be690a67d92eac
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446951"
---
# <a name="importfileex-method"></a><span data-ttu-id="e232c-102">ImportFileEx (Método)</span><span class="sxs-lookup"><span data-stu-id="e232c-102">ImportFileEx Method</span></span>
<span data-ttu-id="e232c-103">Importa el ensamblado indicado o el módulo sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="e232c-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e232c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e232c-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e232c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e232c-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="e232c-106">Nombre completo del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="e232c-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="e232c-107">Nombre opcional del archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="e232c-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="e232c-108">Si es TRUE, se usa ImportTypes (; de lo contrario, la importación se debe realizar manualmente.</span><span class="sxs-lookup"><span data-stu-id="e232c-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="e232c-109">Marcas que se van a pasar al [método OpenScope](../metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="e232c-109">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="e232c-110">Recibe el identificador del archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="e232c-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="e232c-111">Recibe la interfaz de [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) de ámbito de importación de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e232c-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="e232c-112">Se establece en NULL si el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e232c-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="e232c-113">Recibe el recuento de archivos y/o ámbitos importados.</span><span class="sxs-lookup"><span data-stu-id="e232c-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e232c-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e232c-114">Return Value</span></span>  
 <span data-ttu-id="e232c-115">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="e232c-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e232c-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e232c-116">Requirements</span></span>  
 <span data-ttu-id="e232c-117">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="e232c-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e232c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e232c-118">See also</span></span>

- [<span data-ttu-id="e232c-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e232c-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e232c-120">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e232c-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e232c-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="e232c-121">ALink API</span></span>](index.md)
