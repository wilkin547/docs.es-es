---
title: ISymUnmanagedWriter::UsingNamespace (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.UsingNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d0739cc38d1f12967f0daef2d6828e04a256ade6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201850"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="7baf0-102">ISymUnmanagedWriter::UsingNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="7baf0-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="7baf0-103">Especifica que se utiliza el nombre completo del espacio de nombres determinado dentro del ámbito léxico abierto actualmente.</span><span class="sxs-lookup"><span data-stu-id="7baf0-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="7baf0-104">El espacio de nombres se utilizará en todos los ámbitos que se heredan del ámbito abierto actualmente.</span><span class="sxs-lookup"><span data-stu-id="7baf0-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="7baf0-105">Al cerrar el ámbito actual, también se detendrá el uso del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="7baf0-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7baf0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7baf0-106">Syntax</span></span>  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7baf0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7baf0-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="7baf0-108">[in] Un puntero al nombre completo del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="7baf0-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7baf0-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7baf0-109">Return Value</span></span>  
 <span data-ttu-id="7baf0-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="7baf0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7baf0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7baf0-111">Requirements</span></span>  
 <span data-ttu-id="7baf0-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7baf0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7baf0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7baf0-113">See also</span></span>

- [<span data-ttu-id="7baf0-114">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7baf0-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
