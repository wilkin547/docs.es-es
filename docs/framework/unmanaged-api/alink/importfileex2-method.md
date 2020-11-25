---
title: ImportFileEx2 (Método)
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
ms.openlocfilehash: 59149e79e926a0b9a3e549e013bf178e54ddf6fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705181"
---
# <a name="importfileex2-method"></a><span data-ttu-id="65c57-102">ImportFileEx2 (Método)</span><span class="sxs-lookup"><span data-stu-id="65c57-102">ImportFileEx2 Method</span></span>

<span data-ttu-id="65c57-103">Importa ensamblados y módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="65c57-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="65c57-104">Este método es como el [método importFile](importfile-method.md), pero funciona incluso si el archivo que se va a importar no existe en el disco.</span><span class="sxs-lookup"><span data-stu-id="65c57-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65c57-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65c57-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="65c57-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="65c57-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="65c57-107">Nombre del archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="65c57-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="65c57-108">Nombre opcional del archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="65c57-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="65c57-109">Interfaz de [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) de ámbito de importación opcional.</span><span class="sxs-lookup"><span data-stu-id="65c57-109">Optional import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="65c57-110">Si es TRUE, se usa ImportTypes (; de lo contrario, la importación se debe realizar manualmente.</span><span class="sxs-lookup"><span data-stu-id="65c57-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="65c57-111">Marcas que se van a pasar al [método OpenScope](../metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="65c57-111">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="65c57-112">Recibe el identificador único para el ensamblado o el archivo.</span><span class="sxs-lookup"><span data-stu-id="65c57-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="65c57-113">Recibe la interfaz de [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) de ámbito de importación de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="65c57-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="65c57-114">Puede ser NULL si el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="65c57-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="65c57-115">Recibe el número de archivos y/o ámbitos importados.</span><span class="sxs-lookup"><span data-stu-id="65c57-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65c57-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="65c57-116">Return Value</span></span>  

 <span data-ttu-id="65c57-117">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="65c57-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65c57-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65c57-118">Requirements</span></span>  

 <span data-ttu-id="65c57-119">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="65c57-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c57-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65c57-120">See also</span></span>

- [<span data-ttu-id="65c57-121">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="65c57-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="65c57-122">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="65c57-122">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="65c57-123">API de ALink</span><span class="sxs-lookup"><span data-stu-id="65c57-123">ALink API</span></span>](index.md)
