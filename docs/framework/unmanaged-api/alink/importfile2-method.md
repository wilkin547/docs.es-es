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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a03fc24e5ef932d13c0d195f53c703cdd3ff45ff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776940"
---
# <a name="importfile2-method"></a><span data-ttu-id="23f00-102">ImportFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="23f00-102">ImportFile2 Method</span></span>
<span data-ttu-id="23f00-103">Importa ensamblados y módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="23f00-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="23f00-104">Este método es como el [método importFile](importfile-method.md), pero funciona incluso si el archivo que se va a importar no existe en el disco.</span><span class="sxs-lookup"><span data-stu-id="23f00-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23f00-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23f00-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="23f00-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="23f00-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="23f00-107">Nombre del archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="23f00-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="23f00-108">Nombre opcional del archivo de salida que se puede usar para cambiar el nombre del archivo a medida que está vinculado al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="23f00-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="23f00-109">Interfaz de [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) de ámbito opcional.</span><span class="sxs-lookup"><span data-stu-id="23f00-109">Optional scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="23f00-110">Si es TRUE, se usa ImportTypes (; de lo contrario, la importación se debe realizar manualmente.</span><span class="sxs-lookup"><span data-stu-id="23f00-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="23f00-111">Recibe el identificador del archivo o ensamblado.</span><span class="sxs-lookup"><span data-stu-id="23f00-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="23f00-112">Recibe la interfaz de la [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="23f00-112">Receives the [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="23f00-113">Es NULL si el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="23f00-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="23f00-114">Recibe el encontrado de archivos y/o ámbitos importados.</span><span class="sxs-lookup"><span data-stu-id="23f00-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23f00-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="23f00-115">Return Value</span></span>  
 <span data-ttu-id="23f00-116">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="23f00-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23f00-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23f00-117">Requirements</span></span>  
 <span data-ttu-id="23f00-118">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="23f00-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f00-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="23f00-119">See also</span></span>

- [<span data-ttu-id="23f00-120">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23f00-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="23f00-121">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23f00-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="23f00-122">API de ALink</span><span class="sxs-lookup"><span data-stu-id="23f00-122">ALink API</span></span>](index.md)
