---
title: ISymUnmanagedWriter::CloseNamespace (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type:
- apiref
ms.openlocfilehash: 13a433157e0c92653edf234f1f1f885270196ffd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686415"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="96320-102">ISymUnmanagedWriter::CloseNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="96320-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>

<span data-ttu-id="96320-103">Cierra el espacio de nombres abierto más recientemente.</span><span class="sxs-lookup"><span data-stu-id="96320-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96320-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96320-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="96320-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="96320-105">Return Value</span></span>  

 <span data-ttu-id="96320-106">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="96320-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96320-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="96320-107">Requirements</span></span>  

 <span data-ttu-id="96320-108">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="96320-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96320-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96320-109">See also</span></span>

- [<span data-ttu-id="96320-110">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="96320-110">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="96320-111">Método OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="96320-111">OpenNamespace Method</span></span>](isymunmanagedwriter-opennamespace-method.md)
