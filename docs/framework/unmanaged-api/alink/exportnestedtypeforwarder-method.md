---
title: "ExportNestedTypeForwarder (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ExportNestedTypeForwarder
api_location: alink.dll
api_type: COM
f1_keywords: ExportNestedTypeForwarder
helpviewer_keywords: ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eee41e9f71d600a74cc9f74b538ad9e215f0d905
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="a3f99-102">ExportNestedTypeForwarder (Método)</span><span class="sxs-lookup"><span data-stu-id="a3f99-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="a3f99-103">Agrega un reenviador de tipos para un tipo anidado a la tabla de tipos del ensamblado dado.</span><span class="sxs-lookup"><span data-stu-id="a3f99-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3f99-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3f99-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="a3f99-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3f99-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a3f99-106">Id. del ensamblado que se va a exportar desde.</span><span class="sxs-lookup"><span data-stu-id="a3f99-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a3f99-107">Id. de símbolo (token) o ensamblado del archivo que define el tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="a3f99-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="a3f99-108">Símbolo (token) para el tipo.</span><span class="sxs-lookup"><span data-stu-id="a3f99-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="a3f99-109">Símbolo (token) de tipo primario.</span><span class="sxs-lookup"><span data-stu-id="a3f99-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="a3f99-110">Nombre de tipo completo para exportar.</span><span class="sxs-lookup"><span data-stu-id="a3f99-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a3f99-111">`ComType`marca como `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="a3f99-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="a3f99-112">Recibe el token del tipo de exportación.</span><span class="sxs-lookup"><span data-stu-id="a3f99-112">Receives token of export type.</span></span> <span data-ttu-id="a3f99-113">Esto sólo es necesario para emitir tipos anidados.</span><span class="sxs-lookup"><span data-stu-id="a3f99-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3f99-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a3f99-114">Return Value</span></span>  
 <span data-ttu-id="a3f99-115">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="a3f99-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3f99-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3f99-116">Requirements</span></span>  
 <span data-ttu-id="a3f99-117">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="a3f99-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3f99-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3f99-118">See Also</span></span>  
 [<span data-ttu-id="a3f99-119">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3f99-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="a3f99-120">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3f99-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="a3f99-121">API de ALink</span><span class="sxs-lookup"><span data-stu-id="a3f99-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
