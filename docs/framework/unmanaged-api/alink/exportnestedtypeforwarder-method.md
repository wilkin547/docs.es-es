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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 050ed0bbd4da38bede5a56ff95d0243f5f3cf1da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220089"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="1f7b7-102">ExportNestedTypeForwarder (Método)</span><span class="sxs-lookup"><span data-stu-id="1f7b7-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="1f7b7-103">Agrega un reenviador de tipos para un tipo anidado a la tabla de tipos del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="1f7b7-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f7b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f7b7-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="1f7b7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1f7b7-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1f7b7-106">Id. del ensamblado para exportar.</span><span class="sxs-lookup"><span data-stu-id="1f7b7-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1f7b7-107">Identificador de token o el ensamblado del archivo que define el tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="1f7b7-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="1f7b7-108">Símbolo (token) para el tipo.</span><span class="sxs-lookup"><span data-stu-id="1f7b7-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="1f7b7-109">Token del tipo primario.</span><span class="sxs-lookup"><span data-stu-id="1f7b7-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="1f7b7-110">Nombre de tipo completo para exportar.</span><span class="sxs-lookup"><span data-stu-id="1f7b7-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1f7b7-111">`ComType` marca como `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="1f7b7-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="1f7b7-112">Recibe el token del tipo de exportación.</span><span class="sxs-lookup"><span data-stu-id="1f7b7-112">Receives token of export type.</span></span> <span data-ttu-id="1f7b7-113">Esto sólo es necesario para emitir tipos anidados.</span><span class="sxs-lookup"><span data-stu-id="1f7b7-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f7b7-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1f7b7-114">Return Value</span></span>  
 <span data-ttu-id="1f7b7-115">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="1f7b7-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f7b7-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f7b7-116">Requirements</span></span>  
 <span data-ttu-id="1f7b7-117">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="1f7b7-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f7b7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f7b7-118">See also</span></span>

- [<span data-ttu-id="1f7b7-119">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f7b7-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="1f7b7-120">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f7b7-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="1f7b7-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="1f7b7-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
