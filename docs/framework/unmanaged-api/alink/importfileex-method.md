---
title: ImportFileEx (Método)
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a0381ee61a0128a8ae303d44198f8d391b4531a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660624"
---
# <a name="importfileex-method"></a><span data-ttu-id="4e3b9-102">ImportFileEx (Método)</span><span class="sxs-lookup"><span data-stu-id="4e3b9-102">ImportFileEx Method</span></span>
<span data-ttu-id="4e3b9-103">Importaciones indican el ensamblado o módulo sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="4e3b9-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e3b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e3b9-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="4e3b9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e3b9-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="4e3b9-106">Nombre completo del archivo desde el que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="4e3b9-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="4e3b9-107">Nombre opcional del archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="4e3b9-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="4e3b9-108">Si es TRUE, se utiliza ImportTypes, en caso contrario, la importación debe realizarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="4e3b9-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="4e3b9-109">Marcas que se van a pasar a [OpenScope (método)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="4e3b9-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="4e3b9-110">Recibe el identificador del archivo que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="4e3b9-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="4e3b9-111">Recibe el ámbito de la importación de ensamblado [IMetaDataAssemblyImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="4e3b9-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="4e3b9-112">Se establece en NULL si el archivo no es un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4e3b9-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="4e3b9-113">Recibe el recuento de los archivos importados de los ámbitos.</span><span class="sxs-lookup"><span data-stu-id="4e3b9-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e3b9-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4e3b9-114">Return Value</span></span>  
 <span data-ttu-id="4e3b9-115">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="4e3b9-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e3b9-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e3b9-116">Requirements</span></span>  
 <span data-ttu-id="4e3b9-117">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="4e3b9-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e3b9-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e3b9-118">See also</span></span>
- [<span data-ttu-id="4e3b9-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e3b9-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="4e3b9-120">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e3b9-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="4e3b9-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="4e3b9-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
