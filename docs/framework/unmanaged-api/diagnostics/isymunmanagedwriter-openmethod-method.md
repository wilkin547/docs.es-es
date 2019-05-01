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
ms.openlocfilehash: b05ba185a9ad4ab076d29d7d609734d41677b760
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986055"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="b0adf-102">ISymUnmanagedWriter::OpenMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="b0adf-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="b0adf-103">Abre un método en el símbolo que se emite la información.</span><span class="sxs-lookup"><span data-stu-id="b0adf-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="b0adf-104">El método especificado se convierte en el método actual para las llamadas a definir puntos de secuencia, parámetros y ámbitos léxicos.</span><span class="sxs-lookup"><span data-stu-id="b0adf-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="b0adf-105">Hay un ámbito léxico implícito en torno a todo el método.</span><span class="sxs-lookup"><span data-stu-id="b0adf-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="b0adf-106">Volver a abrir un método que se ha cerrado anteriormente, borrará todos los símbolos definidos previamente para ese método.</span><span class="sxs-lookup"><span data-stu-id="b0adf-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="b0adf-107">Puede haber solo un método abierto a la vez.</span><span class="sxs-lookup"><span data-stu-id="b0adf-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0adf-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0adf-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0adf-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b0adf-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="b0adf-110">[in] El token de metadatos para el método que se puede abrir.</span><span class="sxs-lookup"><span data-stu-id="b0adf-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0adf-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b0adf-111">Return Value</span></span>  
 <span data-ttu-id="b0adf-112">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="b0adf-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0adf-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0adf-113">Requirements</span></span>  
 <span data-ttu-id="b0adf-114">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b0adf-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0adf-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0adf-115">See also</span></span>

- [<span data-ttu-id="b0adf-116">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0adf-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="b0adf-117">CloseMethod (método)</span><span class="sxs-lookup"><span data-stu-id="b0adf-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="b0adf-118">OpenMethod2 (método)</span><span class="sxs-lookup"><span data-stu-id="b0adf-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
