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
ms.openlocfilehash: 3cbd0765404a6c5c4a2111d8050795acd3ab72fd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499139"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="acdcc-102">ISymUnmanagedMethod::GetSequencePointCount (Método)</span><span class="sxs-lookup"><span data-stu-id="acdcc-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="acdcc-103">Obtiene el recuento de puntos de secuencia dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="acdcc-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acdcc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acdcc-104">Syntax</span></span>  
  
```  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acdcc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="acdcc-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="acdcc-106">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="acdcc-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acdcc-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="acdcc-107">Return Value</span></span>  
 <span data-ttu-id="acdcc-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="acdcc-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acdcc-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="acdcc-109">Requirements</span></span>  
 <span data-ttu-id="acdcc-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="acdcc-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acdcc-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="acdcc-111">See also</span></span>
- [<span data-ttu-id="acdcc-112">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="acdcc-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
