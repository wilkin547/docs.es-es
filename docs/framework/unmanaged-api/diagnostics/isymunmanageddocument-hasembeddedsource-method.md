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
ms.openlocfilehash: d654f6d57bd784063fc7f87dd9767bdc27ad2776
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615584"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="c7f86-102">ISymUnmanagedDocument::HasEmbeddedSource (Método)</span><span class="sxs-lookup"><span data-stu-id="c7f86-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="c7f86-103">Devuelve `true` si el documento tiene código fuente incrustado en los símbolos de depuración; de lo contrario, devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="c7f86-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7f86-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7f86-104">Syntax</span></span>  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7f86-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c7f86-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c7f86-106">enuncia Puntero a una variable que indica si el documento tiene código fuente incrustado en los símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="c7f86-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7f86-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c7f86-107">Return Value</span></span>  
 <span data-ttu-id="c7f86-108">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="c7f86-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7f86-109">Consulta también</span><span class="sxs-lookup"><span data-stu-id="c7f86-109">See also</span></span>

- [<span data-ttu-id="c7f86-110">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c7f86-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
