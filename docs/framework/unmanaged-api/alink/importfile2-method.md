---
description: 'Más información sobre: método Importfile2 ('
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
ms.openlocfilehash: 98da8ecf4bfc19e52c5a92e6509f6af49afbdd5f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718062"
---
# <a name="importfile2-method"></a><span data-ttu-id="4fef8-103">ImportFile2 (Método)</span><span class="sxs-lookup"><span data-stu-id="4fef8-103">ImportFile2 Method</span></span>

<span data-ttu-id="4fef8-104">Importa ensamblados y módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="4fef8-104">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="4fef8-105">Este método es como el [método importFile](importfile-method.md), pero funciona incluso si el archivo que se va a importar no existe en el disco.</span><span class="sxs-lookup"><span data-stu-id="4fef8-105">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fef8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4fef8-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4fef8-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4fef8-107">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="4fef8-108">Nombre del archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="4fef8-108">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="4fef8-109">Nombre opcional del archivo de salida que se puede usar para cambiar el nombre del archivo a medida que está vinculado al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4fef8-109">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="4fef8-110">Interfaz de [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) de ámbito opcional.</span><span class="sxs-lookup"><span data-stu-id="4fef8-110">Optional scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="4fef8-111">Si es TRUE, se usa ImportTypes (; de lo contrario, la importación se debe realizar manualmente.</span><span class="sxs-lookup"><span data-stu-id="4fef8-111">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="4fef8-112">Recibe el identificador del archivo o ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4fef8-112">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="4fef8-113">Recibe la interfaz de la [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4fef8-113">Receives the [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="4fef8-114">Es NULL si el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4fef8-114">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="4fef8-115">Recibe el encontrado de archivos y/o ámbitos importados.</span><span class="sxs-lookup"><span data-stu-id="4fef8-115">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4fef8-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4fef8-116">Return Value</span></span>  

 <span data-ttu-id="4fef8-117">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="4fef8-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fef8-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fef8-118">Requirements</span></span>  

 <span data-ttu-id="4fef8-119">Requiere ALink. h.</span><span class="sxs-lookup"><span data-stu-id="4fef8-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fef8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fef8-120">See also</span></span>

- [<span data-ttu-id="4fef8-121">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4fef8-121">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="4fef8-122">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4fef8-122">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="4fef8-123">API de ALink</span><span class="sxs-lookup"><span data-stu-id="4fef8-123">ALink API</span></span>](index.md)
