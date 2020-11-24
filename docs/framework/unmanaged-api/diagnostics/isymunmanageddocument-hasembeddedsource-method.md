---
title: ISymUnmanagedDocument::HasEmbeddedSource (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
ms.openlocfilehash: 09bc0f87cd35f12a15566fb525c2ce42990ac69b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688203"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="8b90e-102">ISymUnmanagedDocument::HasEmbeddedSource (Método)</span><span class="sxs-lookup"><span data-stu-id="8b90e-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>

<span data-ttu-id="8b90e-103">Devuelve `true` si el documento tiene código fuente incrustado en los símbolos de depuración; de lo contrario, devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="8b90e-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b90e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b90e-104">Syntax</span></span>  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b90e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8b90e-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="8b90e-106">enuncia Puntero a una variable que indica si el documento tiene código fuente incrustado en los símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="8b90e-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b90e-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8b90e-107">Return Value</span></span>  

 <span data-ttu-id="8b90e-108">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="8b90e-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b90e-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b90e-109">See also</span></span>

- [<span data-ttu-id="8b90e-110">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b90e-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
