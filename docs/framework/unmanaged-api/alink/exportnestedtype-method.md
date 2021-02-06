---
description: 'Más información sobre: método Exportnestedtype ('
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
ms.openlocfilehash: 66cf4c3572857a0e7e99efa966cdb0b9ae2be673
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638149"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="d31ba-103">ExportNestedType (Método)</span><span class="sxs-lookup"><span data-stu-id="d31ba-103">ExportNestedType Method</span></span>

<span data-ttu-id="d31ba-104">Especifica los tipos anidados como exportables.</span><span class="sxs-lookup"><span data-stu-id="d31ba-104">Specifies nested types as exportable.</span></span> <span data-ttu-id="d31ba-105">El [método ExportType](exporttype-method.md) también puede exportar tipos anidados, pero este método es más rápido.</span><span class="sxs-lookup"><span data-stu-id="d31ba-105">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d31ba-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d31ba-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d31ba-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d31ba-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="d31ba-108">IDENTIFICADOR del ensamblado del que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="d31ba-108">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d31ba-109">Token de archivo o ensamblado de archivo que define el tipo que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="d31ba-109">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="d31ba-110">Token de tipo del tipo que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="d31ba-110">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="d31ba-111">Token del tipo primario.</span><span class="sxs-lookup"><span data-stu-id="d31ba-111">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="d31ba-112">Nombre completo del tipo que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="d31ba-112">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d31ba-113">`ComType` marcas como `tdPublic` o `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="d31ba-113">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="d31ba-114">Este valor se puede pasar al [método DefineExportedType (](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="d31ba-114">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="d31ba-115">Recibe el token para el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="d31ba-115">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d31ba-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d31ba-116">Return Value</span></span>  

 <span data-ttu-id="d31ba-117">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="d31ba-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d31ba-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d31ba-118">Requirements</span></span>  

 <span data-ttu-id="d31ba-119">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="d31ba-119">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d31ba-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d31ba-120">See also</span></span>

- [<span data-ttu-id="d31ba-121">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d31ba-121">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d31ba-122">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d31ba-122">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="d31ba-123">API de ALink</span><span class="sxs-lookup"><span data-stu-id="d31ba-123">ALink API</span></span>](index.md)
