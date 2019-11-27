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
ms.openlocfilehash: 889fd4ec3332cbe80a035e13a5145421dc0ed5a9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448894"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="4842f-102">ISymUnmanagedMethod::GetSequencePointCount (Método)</span><span class="sxs-lookup"><span data-stu-id="4842f-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="4842f-103">Obtiene el recuento de puntos de secuencia dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="4842f-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4842f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4842f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4842f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4842f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4842f-106">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="4842f-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4842f-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4842f-107">Return Value</span></span>  
 <span data-ttu-id="4842f-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="4842f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4842f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4842f-109">Requirements</span></span>  
 <span data-ttu-id="4842f-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="4842f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4842f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4842f-111">See also</span></span>

- [<span data-ttu-id="4842f-112">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4842f-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
