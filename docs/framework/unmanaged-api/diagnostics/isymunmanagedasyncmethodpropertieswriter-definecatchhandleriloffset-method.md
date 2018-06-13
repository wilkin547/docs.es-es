---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset (Método)
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce462c4e7e9c8fb11ee74a91f3ece2465a44a834
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425436"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="ff8d1-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="ff8d1-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="ff8d1-103">Establece el IL de desplazamiento para el controlador catch generada por el compilador que encapsula un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="ff8d1-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="ff8d1-104">El desplazamiento IL de la instrucción catch generado se utiliza el depurador para controlar la captura como si fuera código de no usuario, aunque puede ocurrir en un método de código de usuario.</span><span class="sxs-lookup"><span data-stu-id="ff8d1-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="ff8d1-105">En concreto, se utiliza en respuesta a un **CatchHandlerFound** eventos de excepción.</span><span class="sxs-lookup"><span data-stu-id="ff8d1-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff8d1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff8d1-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff8d1-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff8d1-107">Parameters</span></span>  
  
|<span data-ttu-id="ff8d1-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="ff8d1-108">Parameter</span></span>|<span data-ttu-id="ff8d1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff8d1-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="ff8d1-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ff8d1-110">Return Value</span></span>  
 <span data-ttu-id="ff8d1-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="ff8d1-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff8d1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff8d1-112">Requirements</span></span>  
 <span data-ttu-id="ff8d1-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ff8d1-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff8d1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff8d1-114">See Also</span></span>  
 [<span data-ttu-id="ff8d1-115">ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff8d1-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
