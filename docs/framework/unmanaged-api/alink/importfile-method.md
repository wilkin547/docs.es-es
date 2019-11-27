---
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
ms.openlocfilehash: cda6d90865f8ad2b9d565f6a6378c35b03c65bf7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446991"
---
# <a name="importfile-method"></a><span data-ttu-id="1d574-102">ImportFile (Método)</span><span class="sxs-lookup"><span data-stu-id="1d574-102">ImportFile Method</span></span>
<span data-ttu-id="1d574-103">Importa ensamblados y módulos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="1d574-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d574-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d574-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1d574-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1d574-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="1d574-106">Nombre completo del archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="1d574-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="1d574-107">Nombre opcional del archivo de salida que se puede usar para cambiar el nombre del archivo a medida que está vinculado al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1d574-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="1d574-108">Si es TRUE, se usa ImportTypes (; de lo contrario, la importación se debe realizar manualmente.</span><span class="sxs-lookup"><span data-stu-id="1d574-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="1d574-109">Puntero al token en el que se almacenará un identificador de archivo único.</span><span class="sxs-lookup"><span data-stu-id="1d574-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="1d574-110">El archivo puede ser un ensamblado o un archivo.</span><span class="sxs-lookup"><span data-stu-id="1d574-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="1d574-111">Recibe un puntero a la [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md).</span><span class="sxs-lookup"><span data-stu-id="1d574-111">Receives pointer to [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="1d574-112">Puede ser NULL si el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1d574-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="1d574-113">Puntero al recuento de archivos y/o ámbitos que se han importado.</span><span class="sxs-lookup"><span data-stu-id="1d574-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d574-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1d574-114">Return Value</span></span>  
 <span data-ttu-id="1d574-115">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="1d574-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d574-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d574-116">Requirements</span></span>  
 <span data-ttu-id="1d574-117">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="1d574-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d574-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d574-118">See also</span></span>

- [<span data-ttu-id="1d574-119">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d574-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="1d574-120">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d574-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="1d574-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="1d574-121">ALink API</span></span>](index.md)
