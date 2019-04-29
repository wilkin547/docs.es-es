---
title: ISymUnmanagedReader::GetUserEntryPoint (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0267ae8b57c837b097d496c8e119085d03417e36
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670045"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="3e27d-102">ISymUnmanagedReader::GetUserEntryPoint (Método)</span><span class="sxs-lookup"><span data-stu-id="3e27d-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="3e27d-103">Devuelve el método que se especificó como el punto de entrada de usuario para el módulo, si existe.</span><span class="sxs-lookup"><span data-stu-id="3e27d-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="3e27d-104">Por ejemplo, este método podría ser el método del usuario principal en lugar de código auxiliar generado por el compilador antes del método principal.</span><span class="sxs-lookup"><span data-stu-id="3e27d-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e27d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e27d-105">Syntax</span></span>  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e27d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3e27d-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="3e27d-107">[out] Un puntero a una variable que recibe el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="3e27d-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e27d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3e27d-108">Return Value</span></span>  
 <span data-ttu-id="3e27d-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="3e27d-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e27d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e27d-110">Requirements</span></span>  
 <span data-ttu-id="3e27d-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3e27d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e27d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e27d-112">See also</span></span>

- [<span data-ttu-id="3e27d-113">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e27d-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
