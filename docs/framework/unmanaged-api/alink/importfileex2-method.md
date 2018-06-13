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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be6332c76b3dae9c02e1a939286b70438ee14cfb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400684"
---
# <a name="importfileex2-method"></a><span data-ttu-id="741d8-102">ImportFileEx2 (Método)</span><span class="sxs-lookup"><span data-stu-id="741d8-102">ImportFileEx2 Method</span></span>
<span data-ttu-id="741d8-103">Importa ensamblados y módulos no enlazados.</span><span class="sxs-lookup"><span data-stu-id="741d8-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="741d8-104">Este método es similar a [ImportFile (método)](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), pero funciona incluso si el archivo que se va a importar no existe en el disco.</span><span class="sxs-lookup"><span data-stu-id="741d8-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="741d8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="741d8-105">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="741d8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="741d8-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="741d8-107">Nombre del archivo que desea importar.</span><span class="sxs-lookup"><span data-stu-id="741d8-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="741d8-108">Nombre opcional del archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="741d8-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="741d8-109">Ámbito de importación opcional [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="741d8-109">Optional import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="741d8-110">Si es TRUE, se utiliza ImportTypes, en caso contrario, la importación debe realizarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="741d8-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="741d8-111">Marcas que se van a pasar a [OpenScope (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="741d8-111">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="741d8-112">Recibe el identificador único para el ensamblado o el archivo.</span><span class="sxs-lookup"><span data-stu-id="741d8-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="741d8-113">Recibe el ámbito de la importación de ensamblado [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="741d8-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="741d8-114">Puede ser NULL si el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="741d8-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="741d8-115">Recibe el número de archivos y/o ámbitos importados.</span><span class="sxs-lookup"><span data-stu-id="741d8-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="741d8-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="741d8-116">Return Value</span></span>  
 <span data-ttu-id="741d8-117">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="741d8-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="741d8-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="741d8-118">Requirements</span></span>  
 <span data-ttu-id="741d8-119">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="741d8-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="741d8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="741d8-120">See Also</span></span>  
 [<span data-ttu-id="741d8-121">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="741d8-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="741d8-122">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="741d8-122">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="741d8-123">API de ALink</span><span class="sxs-lookup"><span data-stu-id="741d8-123">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
