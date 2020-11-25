---
title: ImportFile2 (Método)
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
ms.openlocfilehash: d02bc53676dd5afb0222a1ea366a8f2bd1f94f62
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705233"
---
# <a name="importfile2-method"></a><span data-ttu-id="bdfa0-102">ImportFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="bdfa0-102">ImportFile2 Method</span></span>

<span data-ttu-id="bdfa0-103">Importa ensamblados y módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="bdfa0-104">Este método es como el [método importFile](importfile-method.md), pero funciona incluso si el archivo que se va a importar no existe en el disco.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdfa0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bdfa0-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdfa0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bdfa0-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="bdfa0-107">Nombre del archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="bdfa0-108">Nombre opcional del archivo de salida que se puede usar para cambiar el nombre del archivo a medida que está vinculado al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="bdfa0-109">Interfaz de [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) de ámbito opcional.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-109">Optional scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="bdfa0-110">Si es TRUE, se usa ImportTypes (; de lo contrario, la importación se debe realizar manualmente.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="bdfa0-111">Recibe el identificador del archivo o ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="bdfa0-112">Recibe la interfaz de la [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="bdfa0-112">Receives the [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="bdfa0-113">Es NULL si el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="bdfa0-114">Recibe el encontrado de archivos y/o ámbitos importados.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bdfa0-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bdfa0-115">Return Value</span></span>  

 <span data-ttu-id="bdfa0-116">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdfa0-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bdfa0-117">Requirements</span></span>  

 <span data-ttu-id="bdfa0-118">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="bdfa0-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdfa0-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bdfa0-119">See also</span></span>

- [<span data-ttu-id="bdfa0-120">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bdfa0-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="bdfa0-121">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bdfa0-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="bdfa0-122">API de ALink</span><span class="sxs-lookup"><span data-stu-id="bdfa0-122">ALink API</span></span>](index.md)
