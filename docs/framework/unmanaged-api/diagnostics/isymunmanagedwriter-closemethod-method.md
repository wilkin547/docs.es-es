---
title: ISymUnmanagedWriter::CloseMethod (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23f77f30b84622dffd8c76bb9302ad564f40ed41
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778190"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="5897d-102">ISymUnmanagedWriter::CloseMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="5897d-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="5897d-103">Cierra el método actual.</span><span class="sxs-lookup"><span data-stu-id="5897d-103">Closes the current method.</span></span> <span data-ttu-id="5897d-104">Una vez cerrado un método, no hay más símbolos se pueden definir dentro de él.</span><span class="sxs-lookup"><span data-stu-id="5897d-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5897d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5897d-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5897d-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5897d-106">Return Value</span></span>  
 <span data-ttu-id="5897d-107">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="5897d-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5897d-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5897d-108">Requirements</span></span>  
 <span data-ttu-id="5897d-109">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5897d-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5897d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5897d-110">See also</span></span>

- [<span data-ttu-id="5897d-111">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5897d-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="5897d-112">OpenMethod (método)</span><span class="sxs-lookup"><span data-stu-id="5897d-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
