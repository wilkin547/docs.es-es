---
title: ISymUnmanagedReader::GetMethod (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type:
- apiref
ms.openlocfilehash: 3f0d0e060bba832080dd8fbfab62f3115fec0aab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689646"
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="d7005-102">ISymUnmanagedReader::GetMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="d7005-102">ISymUnmanagedReader::GetMethod Method</span></span>

<span data-ttu-id="d7005-103">Obtiene un método del lector de símbolos, dado un token de método.</span><span class="sxs-lookup"><span data-stu-id="d7005-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7005-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7005-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7005-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d7005-105">Parameters</span></span>  

 `token`  
 <span data-ttu-id="d7005-106">de Token del método.</span><span class="sxs-lookup"><span data-stu-id="d7005-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d7005-107">enuncia Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="d7005-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7005-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d7005-108">Return Value</span></span>  

 <span data-ttu-id="d7005-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d7005-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7005-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7005-110">Requirements</span></span>  

 <span data-ttu-id="d7005-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d7005-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7005-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7005-112">See also</span></span>

- [<span data-ttu-id="d7005-113">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d7005-113">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
