---
title: "ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54cc369b309d1ffe20d0f3e6a2d4ae4e0443c85f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="cc401-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="cc401-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="cc401-103">Establece el IL de desplazamiento para el controlador catch generada por el compilador que encapsula un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="cc401-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="cc401-104">El desplazamiento IL de la instrucción catch generado se utiliza el depurador para controlar la captura como si fuera código de no usuario, aunque puede ocurrir en un método de código de usuario.</span><span class="sxs-lookup"><span data-stu-id="cc401-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="cc401-105">En concreto, se utiliza en respuesta a un **CatchHandlerFound** eventos de excepción.</span><span class="sxs-lookup"><span data-stu-id="cc401-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc401-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc401-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc401-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cc401-107">Parameters</span></span>  
  
|<span data-ttu-id="cc401-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="cc401-108">Parameter</span></span>|<span data-ttu-id="cc401-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc401-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="cc401-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cc401-110">Return Value</span></span>  
 <span data-ttu-id="cc401-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="cc401-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc401-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc401-112">Requirements</span></span>  
 <span data-ttu-id="cc401-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cc401-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc401-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc401-114">See Also</span></span>  
 [<span data-ttu-id="cc401-115">ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cc401-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
