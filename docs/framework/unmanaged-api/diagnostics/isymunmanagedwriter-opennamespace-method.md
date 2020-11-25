---
title: ISymUnmanagedWriter::OpenNamespace (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
ms.openlocfilehash: 2f64f9f4bde3119f9f089becec5a36d69ed43596
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730066"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="63d60-102">ISymUnmanagedWriter::OpenNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="63d60-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>

<span data-ttu-id="63d60-103">Abre un nuevo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="63d60-103">Opens a new namespace.</span></span> <span data-ttu-id="63d60-104">Llame a este método antes de definir métodos o variables que ocupen un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="63d60-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="63d60-105">Los espacios de nombres se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="63d60-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d60-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63d60-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63d60-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63d60-107">Parameters</span></span>  

 `name`  
 <span data-ttu-id="63d60-108">de Puntero al nombre del nuevo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="63d60-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63d60-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="63d60-109">Return Value</span></span>  

 <span data-ttu-id="63d60-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="63d60-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63d60-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63d60-111">Requirements</span></span>  

 <span data-ttu-id="63d60-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="63d60-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d60-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63d60-113">See also</span></span>

- [<span data-ttu-id="63d60-114">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="63d60-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="63d60-115">Método CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="63d60-115">CloseNamespace Method</span></span>](isymunmanagedwriter-closenamespace-method.md)
