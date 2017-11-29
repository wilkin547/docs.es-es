---
title: "ImportFile (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ImportFile
api_location: alink.dll
api_type: COM
f1_keywords: ImportFile
helpviewer_keywords: ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 46830699ba43c406da313653e1910e8f7a18a2ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="importfile-method"></a><span data-ttu-id="26ab7-102">ImportFile (Método)</span><span class="sxs-lookup"><span data-stu-id="26ab7-102">ImportFile Method</span></span>
<span data-ttu-id="26ab7-103">Importa ensamblados y módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="26ab7-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26ab7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26ab7-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="26ab7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="26ab7-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="26ab7-106">Nombre completo del archivo que desea importar.</span><span class="sxs-lookup"><span data-stu-id="26ab7-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="26ab7-107">Nombre de archivo de salida opcionales que puede usarse para cambiar el nombre del archivo cuando se vincule al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="26ab7-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="26ab7-108">Si es TRUE, se utiliza ImportTypes, en caso contrario, la importación debe realizarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="26ab7-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="26ab7-109">Puntero al símbolo (token) donde se almacenará un identificador de archivo único.</span><span class="sxs-lookup"><span data-stu-id="26ab7-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="26ab7-110">El archivo puede ser un ensamblado o un archivo.</span><span class="sxs-lookup"><span data-stu-id="26ab7-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="26ab7-111">Recibe el puntero a [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span><span class="sxs-lookup"><span data-stu-id="26ab7-111">Receives pointer to [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="26ab7-112">Puede ser NULL si el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="26ab7-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="26ab7-113">Puntero al recuento de archivos y/o ámbitos que se han importado.</span><span class="sxs-lookup"><span data-stu-id="26ab7-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26ab7-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="26ab7-114">Return Value</span></span>  
 <span data-ttu-id="26ab7-115">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="26ab7-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26ab7-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26ab7-116">Requirements</span></span>  
 <span data-ttu-id="26ab7-117">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="26ab7-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26ab7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="26ab7-118">See Also</span></span>  
 [<span data-ttu-id="26ab7-119">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="26ab7-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="26ab7-120">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="26ab7-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="26ab7-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="26ab7-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
