---
title: ISymUnmanagedMethod::GetToken (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1bb9a444d8e8b674d1f173214d8bac427f24e408
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759395"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="805f1-102">ISymUnmanagedMethod::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="805f1-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="805f1-103">Devuelve el token de metadatos para este método.</span><span class="sxs-lookup"><span data-stu-id="805f1-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="805f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="805f1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="805f1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="805f1-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="805f1-106">[out] Un puntero a un `mdMethodDef` que recibe el tamaño, en caracteres, del búfer necesario para contener los metadatos.</span><span class="sxs-lookup"><span data-stu-id="805f1-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="805f1-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="805f1-107">Return Value</span></span>  
 <span data-ttu-id="805f1-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="805f1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="805f1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="805f1-109">Requirements</span></span>  
 <span data-ttu-id="805f1-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="805f1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="805f1-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="805f1-111">See also</span></span>

- [<span data-ttu-id="805f1-112">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="805f1-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
