---
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
ms.openlocfilehash: 45adda6551e1cec994f59acbb0e8d2b5c56c4df6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684816"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="d0e90-102">ExportNestedTypeForwarder (Método)</span><span class="sxs-lookup"><span data-stu-id="d0e90-102">ExportNestedTypeForwarder Method</span></span>

<span data-ttu-id="d0e90-103">Agrega un reenviador de tipos para un tipo anidado a la tabla de tipos del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="d0e90-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0e90-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0e90-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d0e90-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0e90-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="d0e90-106">IDENTIFICADOR del ensamblado del que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="d0e90-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d0e90-107">Token de archivo o ID. de ensamblado del archivo que define el tipo.</span><span class="sxs-lookup"><span data-stu-id="d0e90-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="d0e90-108">Token para el tipo.</span><span class="sxs-lookup"><span data-stu-id="d0e90-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="d0e90-109">Token del tipo primario.</span><span class="sxs-lookup"><span data-stu-id="d0e90-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="d0e90-110">Nombre completo del tipo que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="d0e90-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d0e90-111">`ComType` marcas como `tdPublic` o `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="d0e90-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="d0e90-112">Recibe el token del tipo de exportación.</span><span class="sxs-lookup"><span data-stu-id="d0e90-112">Receives token of export type.</span></span> <span data-ttu-id="d0e90-113">Esto solo es necesario para emitir tipos anidados.</span><span class="sxs-lookup"><span data-stu-id="d0e90-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0e90-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d0e90-114">Return Value</span></span>  

 <span data-ttu-id="d0e90-115">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="d0e90-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0e90-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0e90-116">Requirements</span></span>  

 <span data-ttu-id="d0e90-117">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="d0e90-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0e90-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d0e90-118">See also</span></span>

- [<span data-ttu-id="d0e90-119">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0e90-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d0e90-120">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0e90-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="d0e90-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="d0e90-121">ALink API</span></span>](index.md)
