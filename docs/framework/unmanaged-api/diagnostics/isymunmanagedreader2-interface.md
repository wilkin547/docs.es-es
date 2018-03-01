---
title: ISymUnmanagedReader2 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 93f4b88d891d7b5c1d92006276a290841372aad7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="e0445-102">ISymUnmanagedReader2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0445-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="e0445-103">Representa un lector de símbolos que proporciona acceso a documentos, métodos y variables del sistema en un almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e0445-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="e0445-104">Esta interfaz extiende la [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="e0445-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0445-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e0445-105">Methods</span></span>  
  
|<span data-ttu-id="e0445-106">Método</span><span class="sxs-lookup"><span data-stu-id="e0445-106">Method</span></span>|<span data-ttu-id="e0445-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0445-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e0445-108">GetMethodByVersionPreRemap (método)</span><span class="sxs-lookup"><span data-stu-id="e0445-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="e0445-109">Obtener un método del lector de símbolos, dados un token de método y un número de versión de editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="e0445-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="e0445-110">GetMethodsInDocument (método)</span><span class="sxs-lookup"><span data-stu-id="e0445-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="e0445-111">Obtiene cada método que tiene información de línea en el documento proporcionado.</span><span class="sxs-lookup"><span data-stu-id="e0445-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="e0445-112">GetSymAttributePreRemap (método)</span><span class="sxs-lookup"><span data-stu-id="e0445-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="e0445-113">Obtiene un atributo personalizado basándose en su nombre.</span><span class="sxs-lookup"><span data-stu-id="e0445-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e0445-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0445-114">Requirements</span></span>  
 <span data-ttu-id="e0445-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e0445-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0445-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0445-116">See Also</span></span>  
 [<span data-ttu-id="e0445-117">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="e0445-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="e0445-118">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0445-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
