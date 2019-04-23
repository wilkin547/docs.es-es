---
title: ISymUnmanagedMethod::GetSequencePointCount (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePointCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePointCount
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePointCount method [.NET Framework debugging]
- GetSequencePointCount method [.NET Framework debugging]
ms.assetid: 836133e8-6108-4b9b-b0a9-bce4e08dccda
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9eac17ec9599caba88ddaa73d28abcae538a4d19
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215071"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="e8a09-102">ISymUnmanagedMethod::GetSequencePointCount (Método)</span><span class="sxs-lookup"><span data-stu-id="e8a09-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="e8a09-103">Obtiene el recuento de puntos de secuencia dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="e8a09-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8a09-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8a09-104">Syntax</span></span>  
  
```  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8a09-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e8a09-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e8a09-106">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="e8a09-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8a09-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e8a09-107">Return Value</span></span>  
 <span data-ttu-id="e8a09-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e8a09-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8a09-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8a09-109">Requirements</span></span>  
 <span data-ttu-id="e8a09-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e8a09-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a09-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8a09-111">See also</span></span>

- [<span data-ttu-id="e8a09-112">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8a09-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
