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
ms.openlocfilehash: 76134a2447cbc40b5c97304540d9907648bc89e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719923"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="c4401-102">ISymUnmanagedMethod::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="c4401-102">ISymUnmanagedMethod::GetToken Method</span></span>

<span data-ttu-id="c4401-103">Devuelve el símbolo (token) de metadatos para este método.</span><span class="sxs-lookup"><span data-stu-id="c4401-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4401-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4401-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4401-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c4401-105">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="c4401-106">enuncia Un puntero a un `mdMethodDef` que recibe el tamaño, en caracteres, del búfer necesario para contener los metadatos.</span><span class="sxs-lookup"><span data-stu-id="c4401-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4401-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c4401-107">Return Value</span></span>  

 <span data-ttu-id="c4401-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c4401-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4401-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4401-109">Requirements</span></span>  

 <span data-ttu-id="c4401-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c4401-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4401-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c4401-111">See also</span></span>

- [<span data-ttu-id="c4401-112">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4401-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
