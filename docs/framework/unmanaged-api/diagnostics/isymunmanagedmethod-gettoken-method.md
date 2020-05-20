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
ms.openlocfilehash: 0803f0b55f19b779f5b6608a9f8200d2b085b504
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615162"
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="ac808-102">ISymUnmanagedMethod::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="ac808-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="ac808-103">Devuelve el símbolo (token) de metadatos para este método.</span><span class="sxs-lookup"><span data-stu-id="ac808-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac808-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac808-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac808-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac808-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="ac808-106">enuncia Un puntero a un `mdMethodDef` que recibe el tamaño, en caracteres, del búfer necesario para contener los metadatos.</span><span class="sxs-lookup"><span data-stu-id="ac808-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac808-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ac808-107">Return Value</span></span>  
 <span data-ttu-id="ac808-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="ac808-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac808-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac808-109">Requirements</span></span>  
 <span data-ttu-id="ac808-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ac808-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac808-111">Consulta también</span><span class="sxs-lookup"><span data-stu-id="ac808-111">See also</span></span>

- [<span data-ttu-id="ac808-112">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac808-112">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
