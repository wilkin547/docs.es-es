---
title: "ImportTypes (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ImportTypes
api_location: alink.dll
api_type: COM
f1_keywords: ImportTypes
helpviewer_keywords: ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b8fb83d4e3244010550cb21fedbc6c3b1c5d60d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="importtypes-method"></a><span data-ttu-id="fa413-102">ImportTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="fa413-102">ImportTypes Method</span></span>
<span data-ttu-id="fa413-103">Inicia la importación de los tipos de cada ámbito importado a través de [ImportFile (método)](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="fa413-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa413-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa413-104">Syntax</span></span>  
  
```  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa413-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa413-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fa413-106">Id. del ensamblado que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="fa413-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="fa413-107">Identificador del archivo para importar desde.</span><span class="sxs-lookup"><span data-stu-id="fa413-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="fa413-108">Ámbito de base cero para importar.</span><span class="sxs-lookup"><span data-stu-id="fa413-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="fa413-109">Recibe el identificador de enumerador para los tipos en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="fa413-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="fa413-110">Opcionalmente, recibe [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="fa413-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="fa413-111">Opcionalmente, recibe el recuento de tipos en el ámbito indicado.</span><span class="sxs-lookup"><span data-stu-id="fa413-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa413-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fa413-112">Return Value</span></span>  
 <span data-ttu-id="fa413-113">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="fa413-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa413-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa413-114">Requirements</span></span>  
 <span data-ttu-id="fa413-115">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="fa413-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa413-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa413-116">See Also</span></span>  
 [<span data-ttu-id="fa413-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa413-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="fa413-118">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa413-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="fa413-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="fa413-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
