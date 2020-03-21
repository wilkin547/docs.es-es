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
ms.openlocfilehash: 9ca2167e66ac3aa5bcc0e92ff357eed18d366c67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179413"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="ec5d8-102">ExportNestedType (Método)</span><span class="sxs-lookup"><span data-stu-id="ec5d8-102">ExportNestedType Method</span></span>
<span data-ttu-id="ec5d8-103">Especifica los tipos anidados como exportables.</span><span class="sxs-lookup"><span data-stu-id="ec5d8-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="ec5d8-104">El [método ExportType](exporttype-method.md) también puede exportar tipos anidados, pero este método es más rápido.</span><span class="sxs-lookup"><span data-stu-id="ec5d8-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec5d8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec5d8-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ec5d8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec5d8-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ec5d8-107">ID de ensamblado desde el que exportar.</span><span class="sxs-lookup"><span data-stu-id="ec5d8-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ec5d8-108">Token de archivo o ensamblado de archivo que define el tipo que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="ec5d8-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="ec5d8-109">Escriba el token de tipo que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="ec5d8-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="ec5d8-110">Token de tipo primario.</span><span class="sxs-lookup"><span data-stu-id="ec5d8-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="ec5d8-111">Nombre de tipo completo para exportar.</span><span class="sxs-lookup"><span data-stu-id="ec5d8-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ec5d8-112">`ComType`banderas `tdPublic` como `tdNested`o .</span><span class="sxs-lookup"><span data-stu-id="ec5d8-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="ec5d8-113">Este valor se puede pasar al [método DefineExportedType](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="ec5d8-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="ec5d8-114">Recibe token para el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="ec5d8-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec5d8-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ec5d8-115">Return Value</span></span>  
 <span data-ttu-id="ec5d8-116">Devuelve S_OK si el método se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="ec5d8-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec5d8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec5d8-117">Requirements</span></span>  
 <span data-ttu-id="ec5d8-118">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="ec5d8-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec5d8-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec5d8-119">See also</span></span>

- [<span data-ttu-id="ec5d8-120">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec5d8-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ec5d8-121">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec5d8-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ec5d8-122">API de ALink</span><span class="sxs-lookup"><span data-stu-id="ec5d8-122">ALink API</span></span>](index.md)
