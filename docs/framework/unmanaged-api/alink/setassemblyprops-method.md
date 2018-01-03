---
title: "SetAssemblyProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.SetAssemblyProps
api_location: alink.dll
api_type: COM
f1_keywords: SetAssemblyProps
helpviewer_keywords: SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae13daab0352ad4367c7ad6e06d6c12af23c75bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="99040-102">SetAssemblyProps (Método)</span><span class="sxs-lookup"><span data-stu-id="99040-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="99040-103">Asigna propiedades de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="99040-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99040-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99040-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99040-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99040-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="99040-106">Identificador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="99040-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="99040-107">Archivo que define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="99040-107">File that defines the property.</span></span> <span data-ttu-id="99040-108">Puede ser NULL si `AssemblyID` no indica un archivo netmodule no enlazado.</span><span class="sxs-lookup"><span data-stu-id="99040-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="99040-109">Indica que la opción para modificar.</span><span class="sxs-lookup"><span data-stu-id="99040-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="99040-110">Nuevo valor de la opción.</span><span class="sxs-lookup"><span data-stu-id="99040-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99040-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="99040-111">Return Value</span></span>  
 <span data-ttu-id="99040-112">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="99040-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99040-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99040-113">Requirements</span></span>  
 <span data-ttu-id="99040-114">Requiere alink.h.</span><span class="sxs-lookup"><span data-stu-id="99040-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99040-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="99040-115">See Also</span></span>  
 [<span data-ttu-id="99040-116">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="99040-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="99040-117">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="99040-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="99040-118">API de ALink</span><span class="sxs-lookup"><span data-stu-id="99040-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
