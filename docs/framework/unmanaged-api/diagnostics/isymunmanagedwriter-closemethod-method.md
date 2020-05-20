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
ms.openlocfilehash: fdf24bb8533da7914128f9477987c427442383bb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610124"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="884de-102">ISymUnmanagedWriter::CloseMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="884de-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="884de-103">Cierra el método actual.</span><span class="sxs-lookup"><span data-stu-id="884de-103">Closes the current method.</span></span> <span data-ttu-id="884de-104">Una vez que se cierra un método, no se pueden definir más símbolos en él.</span><span class="sxs-lookup"><span data-stu-id="884de-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="884de-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="884de-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="884de-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="884de-106">Return Value</span></span>  
 <span data-ttu-id="884de-107">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="884de-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="884de-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="884de-108">Requirements</span></span>  
 <span data-ttu-id="884de-109">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="884de-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="884de-110">Consulta también</span><span class="sxs-lookup"><span data-stu-id="884de-110">See also</span></span>

- [<span data-ttu-id="884de-111">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="884de-111">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="884de-112">Método OpenMethod</span><span class="sxs-lookup"><span data-stu-id="884de-112">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
