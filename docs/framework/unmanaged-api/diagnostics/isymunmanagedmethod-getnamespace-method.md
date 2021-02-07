---
description: 'Más información acerca de: ISymUnmanagedMethod:: GetNamespace (método)'
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
ms.openlocfilehash: 8cb211b1047aff31cc4f12d538fee414c578155b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721416"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="e3828-103">ISymUnmanagedMethod::GetNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="e3828-103">ISymUnmanagedMethod::GetNamespace Method</span></span>

<span data-ttu-id="e3828-104">Obtiene el espacio de nombres en el que se define este método.</span><span class="sxs-lookup"><span data-stu-id="e3828-104">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3828-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3828-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3828-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e3828-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="e3828-107">enuncia Puntero que se establece en la interfaz [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="e3828-107">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3828-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e3828-108">Return Value</span></span>  

 <span data-ttu-id="e3828-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e3828-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3828-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3828-110">Requirements</span></span>  

 <span data-ttu-id="e3828-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e3828-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3828-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3828-112">See also</span></span>

- [<span data-ttu-id="e3828-113">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3828-113">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
