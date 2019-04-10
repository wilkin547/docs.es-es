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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211275"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="a43c6-102">ISymUnmanagedReader::GetUserEntryPoint (Método)</span><span class="sxs-lookup"><span data-stu-id="a43c6-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="a43c6-103">Devuelve el método que se especificó como el punto de entrada de usuario para el módulo, si existe.</span><span class="sxs-lookup"><span data-stu-id="a43c6-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="a43c6-104">Por ejemplo, este método podría ser el método del usuario principal en lugar de código auxiliar generado por el compilador antes del método principal.</span><span class="sxs-lookup"><span data-stu-id="a43c6-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a43c6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a43c6-105">Syntax</span></span>  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a43c6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a43c6-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="a43c6-107">[out] Un puntero a una variable que recibe el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="a43c6-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a43c6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a43c6-108">Return Value</span></span>  
 <span data-ttu-id="a43c6-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a43c6-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a43c6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a43c6-110">Requirements</span></span>  
 <span data-ttu-id="a43c6-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a43c6-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a43c6-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a43c6-112">See also</span></span>

- [<span data-ttu-id="a43c6-113">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a43c6-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
