---
title: ISymUnmanagedDocument::GetSourceLength (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
ms.openlocfilehash: e84639c1d63e6935b9b363f01c12bf0fbd3390e3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615623"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="3e5b2-102">ISymUnmanagedDocument::GetSourceLength (Método)</span><span class="sxs-lookup"><span data-stu-id="3e5b2-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="3e5b2-103">Obtiene la longitud, en bytes, del código fuente incrustado.</span><span class="sxs-lookup"><span data-stu-id="3e5b2-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e5b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e5b2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e5b2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3e5b2-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="3e5b2-106">enuncia Puntero a una variable que indica la longitud, en bytes, del código fuente incrustado.</span><span class="sxs-lookup"><span data-stu-id="3e5b2-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e5b2-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3e5b2-107">Return Value</span></span>  
 <span data-ttu-id="3e5b2-108">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="3e5b2-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e5b2-109">Consulta también</span><span class="sxs-lookup"><span data-stu-id="3e5b2-109">See also</span></span>

- [<span data-ttu-id="3e5b2-110">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e5b2-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
