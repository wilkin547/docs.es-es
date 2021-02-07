---
description: 'Más información acerca de: método ImportFile'
title: ImportFile (Método)
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
ms.openlocfilehash: 82c9c7de7cd739ee205dc3695ea651643d01ea3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718166"
---
# <a name="importfile-method"></a><span data-ttu-id="470cb-103">ImportFile (Método)</span><span class="sxs-lookup"><span data-stu-id="470cb-103">ImportFile Method</span></span>

<span data-ttu-id="470cb-104">Importa ensamblados y módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="470cb-104">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="470cb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="470cb-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="470cb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="470cb-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="470cb-107">Nombre completo del archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="470cb-107">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="470cb-108">Nombre opcional del archivo de salida que se puede usar para cambiar el nombre del archivo a medida que está vinculado al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="470cb-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="470cb-109">Si es TRUE, se usa ImportTypes (; de lo contrario, la importación se debe realizar manualmente.</span><span class="sxs-lookup"><span data-stu-id="470cb-109">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="470cb-110">Puntero al token en el que se almacenará un identificador de archivo único.</span><span class="sxs-lookup"><span data-stu-id="470cb-110">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="470cb-111">El archivo puede ser un ensamblado o un archivo.</span><span class="sxs-lookup"><span data-stu-id="470cb-111">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="470cb-112">Recibe un puntero a la [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md).</span><span class="sxs-lookup"><span data-stu-id="470cb-112">Receives pointer to [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="470cb-113">Puede ser NULL si el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="470cb-113">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="470cb-114">Puntero al recuento de archivos y/o ámbitos que se han importado.</span><span class="sxs-lookup"><span data-stu-id="470cb-114">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="470cb-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="470cb-115">Return Value</span></span>  

 <span data-ttu-id="470cb-116">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="470cb-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="470cb-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="470cb-117">Requirements</span></span>  

 <span data-ttu-id="470cb-118">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="470cb-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="470cb-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="470cb-119">See also</span></span>

- [<span data-ttu-id="470cb-120">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="470cb-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="470cb-121">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="470cb-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="470cb-122">API de ALink</span><span class="sxs-lookup"><span data-stu-id="470cb-122">ALink API</span></span>](index.md)
