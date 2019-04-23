---
title: ExportNestedType (Método)
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff159cf794d566be6478ef890c769a0ac72c9b25
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176610"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="b7984-102">ExportNestedType (Método)</span><span class="sxs-lookup"><span data-stu-id="b7984-102">ExportNestedType Method</span></span>
<span data-ttu-id="b7984-103">Especifica los tipos anidados como exportable.</span><span class="sxs-lookup"><span data-stu-id="b7984-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="b7984-104">El [ExportType (método)](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) también puede exportar anidada tipos, pero este método es más rápido.</span><span class="sxs-lookup"><span data-stu-id="b7984-104">The [ExportType Method](../../../../docs/framework/unmanaged-api/alink/exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7984-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7984-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b7984-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7984-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b7984-107">Identificador del ensamblado para exportar.</span><span class="sxs-lookup"><span data-stu-id="b7984-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="b7984-108">Símbolo (token) de archivo o ensamblado del archivo que define el tipo que se realicen exportable.</span><span class="sxs-lookup"><span data-stu-id="b7984-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="b7984-109">Tipo de token del tipo que se realicen exportable.</span><span class="sxs-lookup"><span data-stu-id="b7984-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="b7984-110">Token del tipo primario.</span><span class="sxs-lookup"><span data-stu-id="b7984-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="b7984-111">Nombre de tipo completo para exportar.</span><span class="sxs-lookup"><span data-stu-id="b7984-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b7984-112">`ComType` marca como `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="b7984-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="b7984-113">Este valor puede pasarse a [DefineExportedType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="b7984-113">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="b7984-114">Recibe el token para el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="b7984-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7984-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b7984-115">Return Value</span></span>  
 <span data-ttu-id="b7984-116">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="b7984-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7984-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7984-117">Requirements</span></span>  
 <span data-ttu-id="b7984-118">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="b7984-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7984-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7984-119">See also</span></span>

- [<span data-ttu-id="b7984-120">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7984-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b7984-121">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7984-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b7984-122">API de ALink</span><span class="sxs-lookup"><span data-stu-id="b7984-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
