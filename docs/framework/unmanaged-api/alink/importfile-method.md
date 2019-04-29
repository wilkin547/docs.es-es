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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69e48c6c3179ced167fdc39ae4df859f161727ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61753522"
---
# <a name="importfile-method"></a><span data-ttu-id="228e1-102">ImportFile (Método)</span><span class="sxs-lookup"><span data-stu-id="228e1-102">ImportFile Method</span></span>
<span data-ttu-id="228e1-103">Importa ensamblados y módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="228e1-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="228e1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="228e1-104">Syntax</span></span>  
  
```  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="228e1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="228e1-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="228e1-106">Nombre completo del archivo que desea importar.</span><span class="sxs-lookup"><span data-stu-id="228e1-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="228e1-107">Nombre de archivo de salida opcionales que puede usarse para cambiar el nombre del archivo porque está vinculado en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="228e1-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="228e1-108">Si es TRUE, se utiliza ImportTypes, en caso contrario, la importación debe realizarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="228e1-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="228e1-109">Puntero al símbolo (token) donde se almacenará un identificador de archivo único.</span><span class="sxs-lookup"><span data-stu-id="228e1-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="228e1-110">El archivo puede ser un ensamblado o un archivo.</span><span class="sxs-lookup"><span data-stu-id="228e1-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="228e1-111">Recibe el puntero a [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span><span class="sxs-lookup"><span data-stu-id="228e1-111">Receives pointer to [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="228e1-112">Puede ser NULL si el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="228e1-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="228e1-113">Puntero en el recuento de los archivos de los ámbitos que se han importado.</span><span class="sxs-lookup"><span data-stu-id="228e1-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="228e1-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="228e1-114">Return Value</span></span>  
 <span data-ttu-id="228e1-115">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="228e1-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="228e1-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="228e1-116">Requirements</span></span>  
 <span data-ttu-id="228e1-117">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="228e1-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="228e1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="228e1-118">See also</span></span>

- [<span data-ttu-id="228e1-119">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="228e1-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="228e1-120">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="228e1-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="228e1-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="228e1-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
