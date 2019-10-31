---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset (Método)
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: b108c8c87d3afdbfacb569ab501274e5c45c2e2e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129187"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="7afa2-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="7afa2-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="7afa2-103">Establece el desplazamiento IL para el controlador Catch generado por el compilador que ajusta un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="7afa2-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="7afa2-104">El depurador usa el desplazamiento IL de la instrucción Catch generada para controlar la detección como si fuera un código que no es de usuario, aunque podría producirse en un método de código de usuario.</span><span class="sxs-lookup"><span data-stu-id="7afa2-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="7afa2-105">En concreto, se utiliza en respuesta a un evento de excepción **CatchHandlerFound** .</span><span class="sxs-lookup"><span data-stu-id="7afa2-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7afa2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7afa2-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7afa2-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7afa2-107">Parameters</span></span>  
  
|<span data-ttu-id="7afa2-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="7afa2-108">Parameter</span></span>|<span data-ttu-id="7afa2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7afa2-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="7afa2-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7afa2-110">Return Value</span></span>  
 <span data-ttu-id="7afa2-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="7afa2-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7afa2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7afa2-112">Requirements</span></span>  
 <span data-ttu-id="7afa2-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7afa2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7afa2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7afa2-114">See also</span></span>

- [<span data-ttu-id="7afa2-115">ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7afa2-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
