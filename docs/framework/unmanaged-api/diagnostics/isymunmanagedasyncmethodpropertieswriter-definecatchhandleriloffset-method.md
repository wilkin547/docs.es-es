---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset (Método)
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 923c85a9dff11753a338fcfd3673d3590fca607a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196754"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="36d18-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="36d18-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="36d18-103">Establece el IL de desplazamiento para el controlador catch generado por el compilador que encapsula un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="36d18-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="36d18-104">Se usa el desplazamiento IL de catch generado por el depurador para controlar la captura como si fuera código de no usuario, aunque puede ocurrir en un método de código de usuario.</span><span class="sxs-lookup"><span data-stu-id="36d18-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="36d18-105">En concreto, se utiliza en respuesta a un **CatchHandlerFound** eventos de excepción.</span><span class="sxs-lookup"><span data-stu-id="36d18-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36d18-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36d18-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36d18-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36d18-107">Parameters</span></span>  
  
|<span data-ttu-id="36d18-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="36d18-108">Parameter</span></span>|<span data-ttu-id="36d18-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="36d18-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="36d18-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="36d18-110">Return Value</span></span>  
 <span data-ttu-id="36d18-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="36d18-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36d18-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36d18-112">Requirements</span></span>  
 <span data-ttu-id="36d18-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="36d18-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36d18-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="36d18-114">See also</span></span>

- [<span data-ttu-id="36d18-115">ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36d18-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
