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
ms.openlocfilehash: fded6b95144d4088a2abc8dfcc4ef8eda331c34f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438422"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="db973-102">ExportNestedType (Método)</span><span class="sxs-lookup"><span data-stu-id="db973-102">ExportNestedType Method</span></span>
<span data-ttu-id="db973-103">Especifica los tipos anidados como exportables.</span><span class="sxs-lookup"><span data-stu-id="db973-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="db973-104">El [método ExportType](exporttype-method.md) también puede exportar tipos anidados, pero este método es más rápido.</span><span class="sxs-lookup"><span data-stu-id="db973-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db973-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db973-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="db973-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db973-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="db973-107">IDENTIFICADOR del ensamblado del que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="db973-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="db973-108">Token de archivo o ensamblado de archivo que define el tipo que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="db973-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="db973-109">Token de tipo del tipo que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="db973-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="db973-110">Token del tipo primario.</span><span class="sxs-lookup"><span data-stu-id="db973-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="db973-111">Nombre completo del tipo que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="db973-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="db973-112">`ComType` marcas como `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="db973-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="db973-113">Este valor se puede pasar al [método DefineExportedType (](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="db973-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="db973-114">Recibe el token para el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="db973-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db973-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="db973-115">Return Value</span></span>  
 <span data-ttu-id="db973-116">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="db973-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db973-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db973-117">Requirements</span></span>  
 <span data-ttu-id="db973-118">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="db973-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db973-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="db973-119">See also</span></span>

- [<span data-ttu-id="db973-120">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db973-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="db973-121">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db973-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="db973-122">API de ALink</span><span class="sxs-lookup"><span data-stu-id="db973-122">ALink API</span></span>](index.md)
