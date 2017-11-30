---
title: "ExportNestedType (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location: alink.dll
api_type: COM
f1_keywords: ExportNestedType
helpviewer_keywords: ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 378d1e8b21b8d3993377ac08ff7006c420117bfe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="aba23-102">ExportNestedType (Método)</span><span class="sxs-lookup"><span data-stu-id="aba23-102">ExportNestedType Method</span></span>
<span data-ttu-id="aba23-103">Especifica los tipos anidados como exportable.</span><span class="sxs-lookup"><span data-stu-id="aba23-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="aba23-104">El [ExportType (método)](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) puede también tipos de exportación anidado, pero este método es más rápido.</span><span class="sxs-lookup"><span data-stu-id="aba23-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aba23-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aba23-105">Syntax</span></span>  
  
```  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;   
```  
  
#### <a name="parameters"></a><span data-ttu-id="aba23-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aba23-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="aba23-107">Id. del ensamblado que se va a exportar desde.</span><span class="sxs-lookup"><span data-stu-id="aba23-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="aba23-108">Símbolo (token) de archivo o ensamblado del archivo que define el tipo que realizarse exportable.</span><span class="sxs-lookup"><span data-stu-id="aba23-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="aba23-109">Símbolo (token) de tipo del tipo hacer exportable.</span><span class="sxs-lookup"><span data-stu-id="aba23-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="aba23-110">Símbolo (token) de tipo primario.</span><span class="sxs-lookup"><span data-stu-id="aba23-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="aba23-111">Nombre de tipo completo para exportar.</span><span class="sxs-lookup"><span data-stu-id="aba23-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="aba23-112">`ComType`marca como `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="aba23-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="aba23-113">Este valor puede pasarse a [DefineExportedType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="aba23-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="aba23-114">Recibe el token de tipos exportada.</span><span class="sxs-lookup"><span data-stu-id="aba23-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aba23-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aba23-115">Return Value</span></span>  
 <span data-ttu-id="aba23-116">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="aba23-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aba23-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aba23-117">Requirements</span></span>  
 <span data-ttu-id="aba23-118">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="aba23-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aba23-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="aba23-119">See Also</span></span>  
 [<span data-ttu-id="aba23-120">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aba23-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="aba23-121">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aba23-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="aba23-122">API de ALink</span><span class="sxs-lookup"><span data-stu-id="aba23-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
