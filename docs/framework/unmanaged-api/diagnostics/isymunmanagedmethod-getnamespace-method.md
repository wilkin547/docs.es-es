---
title: ISymUnmanagedMethod::GetNamespace (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
ms.openlocfilehash: 7e26c272ee1ecf03f7d2a347cf7ca2cc3efa2122
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699565"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="e763b-102">ISymUnmanagedMethod::GetNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="e763b-102">ISymUnmanagedMethod::GetNamespace Method</span></span>

<span data-ttu-id="e763b-103">Obtiene el espacio de nombres en el que se define este método.</span><span class="sxs-lookup"><span data-stu-id="e763b-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e763b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e763b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e763b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e763b-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="e763b-106">enuncia Puntero que se establece en la interfaz [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="e763b-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e763b-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e763b-107">Return Value</span></span>  

 <span data-ttu-id="e763b-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e763b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e763b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e763b-109">Requirements</span></span>  

 <span data-ttu-id="e763b-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e763b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e763b-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e763b-111">See also</span></span>

- [<span data-ttu-id="e763b-112">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e763b-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
