---
title: "ExportTypeForwarder (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ExportTypeForwarder
api_location: alink.dll
api_type: COM
f1_keywords: ExportTypeForwarder
helpviewer_keywords: ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0f117d64673729113d917d700e3a26f9723b5a6e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="477aa-102">ExportTypeForwarder (Método)</span><span class="sxs-lookup"><span data-stu-id="477aa-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="477aa-103">Agrega un reenviador de tipos a la tabla de tipos del ensamblado dado.</span><span class="sxs-lookup"><span data-stu-id="477aa-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="477aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="477aa-104">Syntax</span></span>  
  
```  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="477aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="477aa-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="477aa-106">Referencia al ensamblado al que hace referencia el reenviador de tipos.</span><span class="sxs-lookup"><span data-stu-id="477aa-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="477aa-107">Nombre de tipo completo para exportar.</span><span class="sxs-lookup"><span data-stu-id="477aa-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="477aa-108">`ComType`marca como `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="477aa-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="477aa-109">Este valor puede pasarse a [DefineExportedType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="477aa-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="477aa-110">Recibe el token del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="477aa-110">Receives the token of the exported type.</span></span> <span data-ttu-id="477aa-111">Esto sólo es necesario para emitir tipos anidados.</span><span class="sxs-lookup"><span data-stu-id="477aa-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="477aa-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="477aa-112">Return Value</span></span>  
 <span data-ttu-id="477aa-113">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="477aa-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="477aa-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="477aa-114">Requirements</span></span>  
 <span data-ttu-id="477aa-115">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="477aa-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="477aa-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="477aa-116">See Also</span></span>  
 [<span data-ttu-id="477aa-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="477aa-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="477aa-118">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="477aa-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="477aa-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="477aa-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
