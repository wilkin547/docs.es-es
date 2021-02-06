---
description: 'Más información sobre: método Exporttypeforwarder ('
title: ExportTypeForwarder (Método)
ms.date: 03/30/2017
api_name:
- IALink.ExportTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportTypeForwarder
helpviewer_keywords:
- ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type:
- apiref
ms.openlocfilehash: 59fb74c83f6d30dda87d908353795fb218190022
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637994"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="44e0b-103">ExportTypeForwarder (Método)</span><span class="sxs-lookup"><span data-stu-id="44e0b-103">ExportTypeForwarder Method</span></span>

<span data-ttu-id="44e0b-104">Agrega un reenviador de tipos a la tabla de tipos del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="44e0b-104">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44e0b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44e0b-105">Syntax</span></span>  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="44e0b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="44e0b-106">Parameters</span></span>  

 `tkAssemblyRef`  
 <span data-ttu-id="44e0b-107">Referencia al ensamblado al que hace referencia el reenviador de tipos.</span><span class="sxs-lookup"><span data-stu-id="44e0b-107">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="44e0b-108">Nombre completo del tipo que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="44e0b-108">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="44e0b-109">`ComType` marcas como `tdPublic` o `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="44e0b-109">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="44e0b-110">Este valor se puede pasar al [método DefineExportedType (](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="44e0b-110">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="44e0b-111">Recibe el token del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="44e0b-111">Receives the token of the exported type.</span></span> <span data-ttu-id="44e0b-112">Esto solo es necesario para emitir tipos anidados.</span><span class="sxs-lookup"><span data-stu-id="44e0b-112">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44e0b-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="44e0b-113">Return Value</span></span>  

 <span data-ttu-id="44e0b-114">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="44e0b-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44e0b-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44e0b-115">Requirements</span></span>  

 <span data-ttu-id="44e0b-116">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="44e0b-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e0b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="44e0b-117">See also</span></span>

- [<span data-ttu-id="44e0b-118">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="44e0b-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="44e0b-119">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="44e0b-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="44e0b-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="44e0b-120">ALink API</span></span>](index.md)
