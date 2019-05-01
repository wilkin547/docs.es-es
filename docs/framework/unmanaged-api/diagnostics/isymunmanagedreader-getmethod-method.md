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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ab6228866434b35525b16e97b8cba718b849dea1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993348"
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="dbcb1-102">ISymUnmanagedReader::GetMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="dbcb1-102">ISymUnmanagedReader::GetMethod Method</span></span>
<span data-ttu-id="dbcb1-103">Obtiene un método del lector de símbolos, dado un token de método.</span><span class="sxs-lookup"><span data-stu-id="dbcb1-103">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbcb1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dbcb1-104">Syntax</span></span>  
  
```  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbcb1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dbcb1-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="dbcb1-106">[in] El token del método.</span><span class="sxs-lookup"><span data-stu-id="dbcb1-106">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="dbcb1-107">[out] Un puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="dbcb1-107">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbcb1-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="dbcb1-108">Return Value</span></span>  
 <span data-ttu-id="dbcb1-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="dbcb1-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbcb1-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dbcb1-110">Requirements</span></span>  
 <span data-ttu-id="dbcb1-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dbcb1-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbcb1-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbcb1-112">See also</span></span>

- [<span data-ttu-id="dbcb1-113">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dbcb1-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
