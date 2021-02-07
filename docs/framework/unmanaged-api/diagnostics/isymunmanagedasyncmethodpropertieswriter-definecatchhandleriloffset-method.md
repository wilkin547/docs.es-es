---
description: 'Más información acerca de: ISymUnmanagedAsyncMethodPropertiesWriter::D efineCatchHandlerILOffset (método)'
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset (Método)
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: fcb2c6efa7ea83252a46a9b08cdfa7b2c14f09d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737797"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="bf5e9-103">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="bf5e9-103">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>

<span data-ttu-id="bf5e9-104">Establece el desplazamiento IL para el controlador Catch generado por el compilador que ajusta un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="bf5e9-104">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="bf5e9-105">El depurador usa el desplazamiento IL de la instrucción Catch generada para controlar la detección como si fuera un código que no es de usuario, aunque podría producirse en un método de código de usuario.</span><span class="sxs-lookup"><span data-stu-id="bf5e9-105">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="bf5e9-106">En concreto, se utiliza en respuesta a un evento de excepción **CatchHandlerFound** .</span><span class="sxs-lookup"><span data-stu-id="bf5e9-106">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf5e9-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf5e9-107">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf5e9-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf5e9-108">Parameters</span></span>  
  
|<span data-ttu-id="bf5e9-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="bf5e9-109">Parameter</span></span>|<span data-ttu-id="bf5e9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf5e9-110">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="bf5e9-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bf5e9-111">Return Value</span></span>  

 <span data-ttu-id="bf5e9-112">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="bf5e9-112">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf5e9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf5e9-113">Requirements</span></span>  

 <span data-ttu-id="bf5e9-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="bf5e9-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf5e9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf5e9-115">See also</span></span>

- [<span data-ttu-id="bf5e9-116">ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf5e9-116">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
