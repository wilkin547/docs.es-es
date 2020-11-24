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
ms.openlocfilehash: 69c99e2facfcb9077c3fc4131186ba3882c7cef6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684842"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="705e7-102">ExportNestedType (Método)</span><span class="sxs-lookup"><span data-stu-id="705e7-102">ExportNestedType Method</span></span>

<span data-ttu-id="705e7-103">Especifica los tipos anidados como exportables.</span><span class="sxs-lookup"><span data-stu-id="705e7-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="705e7-104">El [método ExportType](exporttype-method.md) también puede exportar tipos anidados, pero este método es más rápido.</span><span class="sxs-lookup"><span data-stu-id="705e7-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="705e7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="705e7-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="705e7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="705e7-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="705e7-107">IDENTIFICADOR del ensamblado del que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="705e7-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="705e7-108">Token de archivo o ensamblado de archivo que define el tipo que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="705e7-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="705e7-109">Token de tipo del tipo que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="705e7-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="705e7-110">Token del tipo primario.</span><span class="sxs-lookup"><span data-stu-id="705e7-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="705e7-111">Nombre completo del tipo que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="705e7-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="705e7-112">`ComType` marcas como `tdPublic` o `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="705e7-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="705e7-113">Este valor se puede pasar al [método DefineExportedType (](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="705e7-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="705e7-114">Recibe el token para el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="705e7-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="705e7-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="705e7-115">Return Value</span></span>  

 <span data-ttu-id="705e7-116">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="705e7-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="705e7-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="705e7-117">Requirements</span></span>  

 <span data-ttu-id="705e7-118">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="705e7-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="705e7-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="705e7-119">See also</span></span>

- [<span data-ttu-id="705e7-120">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="705e7-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="705e7-121">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="705e7-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="705e7-122">API de ALink</span><span class="sxs-lookup"><span data-stu-id="705e7-122">ALink API</span></span>](index.md)
