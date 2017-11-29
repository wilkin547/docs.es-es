---
title: "ISymUnmanagedWriter::OpenMethod (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.OpenMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 61d63fb96635e34e07c3997c1aad838e67c70742
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="76ac3-102">ISymUnmanagedWriter::OpenMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="76ac3-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="76ac3-103">Abre un método en el símbolo que se emite la información.</span><span class="sxs-lookup"><span data-stu-id="76ac3-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="76ac3-104">El método especificado se convierte en el método actual para las llamadas definir puntos de secuencia, parámetros y ámbitos léxicos.</span><span class="sxs-lookup"><span data-stu-id="76ac3-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="76ac3-105">Hay un ámbito léxico implícito en torno al método completo.</span><span class="sxs-lookup"><span data-stu-id="76ac3-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="76ac3-106">Volver a abrir un método que se cerró anteriormente, borrará todos los símbolos definidos previamente para ese método.</span><span class="sxs-lookup"><span data-stu-id="76ac3-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="76ac3-107">Puede haber solo un método abierto a la vez.</span><span class="sxs-lookup"><span data-stu-id="76ac3-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76ac3-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76ac3-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76ac3-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76ac3-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="76ac3-110">[in] El token de metadatos para el método que se abran.</span><span class="sxs-lookup"><span data-stu-id="76ac3-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76ac3-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="76ac3-111">Return Value</span></span>  
 <span data-ttu-id="76ac3-112">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="76ac3-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76ac3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76ac3-113">Requirements</span></span>  
 <span data-ttu-id="76ac3-114">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="76ac3-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ac3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="76ac3-115">See Also</span></span>  
 [<span data-ttu-id="76ac3-116">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76ac3-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="76ac3-117">CloseMethod (método)</span><span class="sxs-lookup"><span data-stu-id="76ac3-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)  
 [<span data-ttu-id="76ac3-118">OpenMethod2 (método)</span><span class="sxs-lookup"><span data-stu-id="76ac3-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
