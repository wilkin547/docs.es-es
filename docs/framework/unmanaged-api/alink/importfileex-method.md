---
title: "ImportFileEx (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.ImportFileEx
api_location: alink.dll
api_type: COM
f1_keywords: ImportFileEx
helpviewer_keywords: ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dc2af9db27c5194a1bdcef875b8db8d458d0edfe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="importfileex-method"></a><span data-ttu-id="bd7a9-102">ImportFileEx (Método)</span><span class="sxs-lookup"><span data-stu-id="bd7a9-102">ImportFileEx Method</span></span>
<span data-ttu-id="bd7a9-103">Importaciones indican el ensamblado o módulo no enlazado.</span><span class="sxs-lookup"><span data-stu-id="bd7a9-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd7a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd7a9-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="bd7a9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd7a9-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="bd7a9-106">Nombre completo del archivo del que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="bd7a9-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="bd7a9-107">Nombre opcional del archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="bd7a9-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="bd7a9-108">Si es TRUE, se utiliza ImportTypes, en caso contrario, la importación debe realizarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="bd7a9-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="bd7a9-109">Marcas que se van a pasar a [OpenScope (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="bd7a9-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="bd7a9-110">Recibe el identificador del archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="bd7a9-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="bd7a9-111">Recibe el ámbito de la importación de ensamblado [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="bd7a9-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="bd7a9-112">Se establece en NULL si el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bd7a9-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="bd7a9-113">Recibe el recuento de archivos y/o ámbitos importados.</span><span class="sxs-lookup"><span data-stu-id="bd7a9-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd7a9-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bd7a9-114">Return Value</span></span>  
 <span data-ttu-id="bd7a9-115">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="bd7a9-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd7a9-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd7a9-116">Requirements</span></span>  
 <span data-ttu-id="bd7a9-117">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="bd7a9-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd7a9-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd7a9-118">See Also</span></span>  
 [<span data-ttu-id="bd7a9-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd7a9-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="bd7a9-120">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd7a9-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="bd7a9-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="bd7a9-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
