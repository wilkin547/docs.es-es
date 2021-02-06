---
description: 'Más información sobre: método Exportnestedtypeforwarder ('
title: ExportNestedTypeForwarder (Método)
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
ms.openlocfilehash: fd791e3fea76338f191fcf924d56720d257d2e8b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638111"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="7442f-103">ExportNestedTypeForwarder (Método)</span><span class="sxs-lookup"><span data-stu-id="7442f-103">ExportNestedTypeForwarder Method</span></span>

<span data-ttu-id="7442f-104">Agrega un reenviador de tipos para un tipo anidado a la tabla de tipos del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="7442f-104">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7442f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7442f-105">Syntax</span></span>  
  
```cpp  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7442f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7442f-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="7442f-107">IDENTIFICADOR del ensamblado del que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="7442f-107">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="7442f-108">Token de archivo o ID. de ensamblado del archivo que define el tipo.</span><span class="sxs-lookup"><span data-stu-id="7442f-108">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="7442f-109">Token para el tipo.</span><span class="sxs-lookup"><span data-stu-id="7442f-109">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="7442f-110">Token del tipo primario.</span><span class="sxs-lookup"><span data-stu-id="7442f-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="7442f-111">Nombre completo del tipo que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="7442f-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7442f-112">`ComType` marcas como `tdPublic` o `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="7442f-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="7442f-113">Recibe el token del tipo de exportación.</span><span class="sxs-lookup"><span data-stu-id="7442f-113">Receives token of export type.</span></span> <span data-ttu-id="7442f-114">Esto solo es necesario para emitir tipos anidados.</span><span class="sxs-lookup"><span data-stu-id="7442f-114">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7442f-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7442f-115">Return Value</span></span>  

 <span data-ttu-id="7442f-116">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="7442f-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7442f-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7442f-117">Requirements</span></span>  

 <span data-ttu-id="7442f-118">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="7442f-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7442f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7442f-119">See also</span></span>

- [<span data-ttu-id="7442f-120">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7442f-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="7442f-121">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7442f-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="7442f-122">API de ALink</span><span class="sxs-lookup"><span data-stu-id="7442f-122">ALink API</span></span>](index.md)
