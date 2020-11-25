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
ms.openlocfilehash: fcf250f10baf4c65cd1c8c918655e4b9f4f5cc4b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731740"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="ca693-102">ISymUnmanagedWriter::CloseMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="ca693-102">ISymUnmanagedWriter::CloseMethod Method</span></span>

<span data-ttu-id="ca693-103">Cierra el método actual.</span><span class="sxs-lookup"><span data-stu-id="ca693-103">Closes the current method.</span></span> <span data-ttu-id="ca693-104">Una vez que se cierra un método, no se pueden definir más símbolos en él.</span><span class="sxs-lookup"><span data-stu-id="ca693-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca693-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca693-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ca693-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ca693-106">Return Value</span></span>  

 <span data-ttu-id="ca693-107">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="ca693-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca693-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca693-108">Requirements</span></span>  

 <span data-ttu-id="ca693-109">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ca693-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca693-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca693-110">See also</span></span>

- [<span data-ttu-id="ca693-111">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca693-111">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="ca693-112">Método OpenMethod</span><span class="sxs-lookup"><span data-stu-id="ca693-112">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
