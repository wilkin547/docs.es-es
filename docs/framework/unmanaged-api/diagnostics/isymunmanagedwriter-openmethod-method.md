---
description: 'Más información acerca de: ISymUnmanagedWriter:: Openmethod ((método)'
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
ms.openlocfilehash: 2cf7e6bf7c632449c25a2b49c7658fa7b1cc287e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762232"
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="e4b42-103">ISymUnmanagedWriter::OpenMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="e4b42-103">ISymUnmanagedWriter::OpenMethod Method</span></span>

<span data-ttu-id="e4b42-104">Abre un método en el que se emite información de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e4b42-104">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="e4b42-105">El método especificado se convierte en el método actual para que las llamadas definan los puntos de secuencia, los parámetros y los ámbitos léxicos.</span><span class="sxs-lookup"><span data-stu-id="e4b42-105">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="e4b42-106">Hay un ámbito léxico implícito en torno al método completo.</span><span class="sxs-lookup"><span data-stu-id="e4b42-106">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="e4b42-107">Al volver a abrir un método que se cerró previamente, se borran los símbolos definidos previamente para ese método.</span><span class="sxs-lookup"><span data-stu-id="e4b42-107">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="e4b42-108">Solo puede haber un método abierto a la vez.</span><span class="sxs-lookup"><span data-stu-id="e4b42-108">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4b42-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4b42-109">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4b42-110">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e4b42-110">Parameters</span></span>  

 `method`  
 <span data-ttu-id="e4b42-111">de Símbolo (token) de metadatos para el método que se va a abrir.</span><span class="sxs-lookup"><span data-stu-id="e4b42-111">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4b42-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e4b42-112">Return Value</span></span>  

 <span data-ttu-id="e4b42-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e4b42-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4b42-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4b42-114">Requirements</span></span>  

 <span data-ttu-id="e4b42-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e4b42-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4b42-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4b42-116">See also</span></span>

- [<span data-ttu-id="e4b42-117">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e4b42-117">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="e4b42-118">Método CloseMethod</span><span class="sxs-lookup"><span data-stu-id="e4b42-118">CloseMethod Method</span></span>](isymunmanagedwriter-closemethod-method.md)
- [<span data-ttu-id="e4b42-119">Método OpenMethod2</span><span class="sxs-lookup"><span data-stu-id="e4b42-119">OpenMethod2 Method</span></span>](isymunmanagedwriter3-openmethod2-method.md)
