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
ms.openlocfilehash: cda30f3c73bf75c37ff79fc415e02382b053807e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614492"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="a5360-102">ISymUnmanagedMethod::GetNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="a5360-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="a5360-103">Obtiene el espacio de nombres en el que se define este método.</span><span class="sxs-lookup"><span data-stu-id="a5360-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5360-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5360-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5360-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5360-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a5360-106">enuncia Puntero que se establece en la interfaz [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="a5360-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5360-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a5360-107">Return Value</span></span>  
 <span data-ttu-id="a5360-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a5360-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5360-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5360-109">Requirements</span></span>  
 <span data-ttu-id="a5360-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="a5360-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5360-111">Consulta también</span><span class="sxs-lookup"><span data-stu-id="a5360-111">See also</span></span>

- [<span data-ttu-id="a5360-112">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5360-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
