---
title: GetScope Method1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetScope
api_location: alink.dll
api_type: COM
f1_keywords: GetScope
helpviewer_keywords: GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b3ebcb90142cc70a2d246d2e9ea6c42babe83b18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="getscope-method1"></a><span data-ttu-id="bb152-102">GetScope Method1</span><span class="sxs-lookup"><span data-stu-id="bb152-102">GetScope Method1</span></span>
<span data-ttu-id="bb152-103">Obtiene un ámbito de importación.</span><span class="sxs-lookup"><span data-stu-id="bb152-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb152-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb152-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb152-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bb152-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="bb152-106">Identificador único del ensamblado que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="bb152-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="bb152-107">Identificador único del archivo que se va a importar desde.</span><span class="sxs-lookup"><span data-stu-id="bb152-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="bb152-108">Ámbito de base cero para importar.</span><span class="sxs-lookup"><span data-stu-id="bb152-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="bb152-109">Recibe [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="bb152-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb152-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bb152-110">Return Value</span></span>  
 <span data-ttu-id="bb152-111">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="bb152-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb152-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb152-112">Requirements</span></span>  
 <span data-ttu-id="bb152-113">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="bb152-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb152-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb152-114">See Also</span></span>  
 [<span data-ttu-id="bb152-115">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb152-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="bb152-116">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb152-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="bb152-117">API de ALink</span><span class="sxs-lookup"><span data-stu-id="bb152-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
