---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset (Método)
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: 58dde2fcce3f4bf578907171e5b575c30c678cfc
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441778"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="3a1d5-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="3a1d5-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="3a1d5-103">Establece el desplazamiento IL para el controlador Catch generado por el compilador que ajusta un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="3a1d5-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="3a1d5-104">El depurador usa el desplazamiento IL de la instrucción Catch generada para controlar la detección como si fuera un código que no es de usuario, aunque podría producirse en un método de código de usuario.</span><span class="sxs-lookup"><span data-stu-id="3a1d5-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="3a1d5-105">En concreto, se utiliza en respuesta a un evento de excepción **CatchHandlerFound** .</span><span class="sxs-lookup"><span data-stu-id="3a1d5-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a1d5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a1d5-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a1d5-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a1d5-107">Parameters</span></span>  
  
|<span data-ttu-id="3a1d5-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="3a1d5-108">Parameter</span></span>|<span data-ttu-id="3a1d5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a1d5-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="3a1d5-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3a1d5-110">Return Value</span></span>  
 <span data-ttu-id="3a1d5-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="3a1d5-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a1d5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a1d5-112">Requirements</span></span>  
 <span data-ttu-id="3a1d5-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3a1d5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a1d5-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="3a1d5-114">See also</span></span>

- [<span data-ttu-id="3a1d5-115">ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a1d5-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
