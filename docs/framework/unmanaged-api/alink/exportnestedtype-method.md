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
ms.workload: dotnet
ms.openlocfilehash: e6d40fffb2d40012d69599ad1bfcdbdaf454aa02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="bb895-102">ExportNestedType (Método)</span><span class="sxs-lookup"><span data-stu-id="bb895-102">ExportNestedType Method</span></span>
<span data-ttu-id="bb895-103">Especifica los tipos anidados como exportable.</span><span class="sxs-lookup"><span data-stu-id="bb895-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="bb895-104">El [ExportType (método)](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) puede también tipos de exportación anidado, pero este método es más rápido.</span><span class="sxs-lookup"><span data-stu-id="bb895-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb895-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb895-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="bb895-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bb895-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="bb895-107">Id. del ensamblado que se va a exportar desde.</span><span class="sxs-lookup"><span data-stu-id="bb895-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="bb895-108">Símbolo (token) de archivo o ensamblado del archivo que define el tipo que realizarse exportable.</span><span class="sxs-lookup"><span data-stu-id="bb895-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="bb895-109">Símbolo (token) de tipo del tipo hacer exportable.</span><span class="sxs-lookup"><span data-stu-id="bb895-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="bb895-110">Símbolo (token) de tipo primario.</span><span class="sxs-lookup"><span data-stu-id="bb895-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="bb895-111">Nombre de tipo completo para exportar.</span><span class="sxs-lookup"><span data-stu-id="bb895-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="bb895-112">`ComType`marca como `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="bb895-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="bb895-113">Este valor puede pasarse a [DefineExportedType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="bb895-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="bb895-114">Recibe el token de tipos exportada.</span><span class="sxs-lookup"><span data-stu-id="bb895-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb895-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bb895-115">Return Value</span></span>  
 <span data-ttu-id="bb895-116">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="bb895-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb895-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb895-117">Requirements</span></span>  
 <span data-ttu-id="bb895-118">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="bb895-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb895-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb895-119">See Also</span></span>  
 [<span data-ttu-id="bb895-120">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb895-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="bb895-121">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb895-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="bb895-122">API de ALink</span><span class="sxs-lookup"><span data-stu-id="bb895-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
