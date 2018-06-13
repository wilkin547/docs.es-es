---
title: ISymUnmanagedWriter::OpenMethod (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc41acd6a4f2ef2557d3b39523c5e398c887c454
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427913"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="c71d2-102">ISymUnmanagedWriter::OpenMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="c71d2-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="c71d2-103">Abre un método en el símbolo que se emite la información.</span><span class="sxs-lookup"><span data-stu-id="c71d2-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="c71d2-104">El método especificado se convierte en el método actual para las llamadas definir puntos de secuencia, parámetros y ámbitos léxicos.</span><span class="sxs-lookup"><span data-stu-id="c71d2-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="c71d2-105">Hay un ámbito léxico implícito en torno al método completo.</span><span class="sxs-lookup"><span data-stu-id="c71d2-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="c71d2-106">Volver a abrir un método que se cerró anteriormente, borrará todos los símbolos definidos previamente para ese método.</span><span class="sxs-lookup"><span data-stu-id="c71d2-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="c71d2-107">Puede haber solo un método abierto a la vez.</span><span class="sxs-lookup"><span data-stu-id="c71d2-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c71d2-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c71d2-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c71d2-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c71d2-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="c71d2-110">[in] El token de metadatos para el método que se abran.</span><span class="sxs-lookup"><span data-stu-id="c71d2-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c71d2-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c71d2-111">Return Value</span></span>  
 <span data-ttu-id="c71d2-112">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c71d2-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c71d2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c71d2-113">Requirements</span></span>  
 <span data-ttu-id="c71d2-114">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c71d2-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c71d2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c71d2-115">See Also</span></span>  
 [<span data-ttu-id="c71d2-116">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c71d2-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="c71d2-117">CloseMethod (método)</span><span class="sxs-lookup"><span data-stu-id="c71d2-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)  
 [<span data-ttu-id="c71d2-118">OpenMethod2 (método)</span><span class="sxs-lookup"><span data-stu-id="c71d2-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
