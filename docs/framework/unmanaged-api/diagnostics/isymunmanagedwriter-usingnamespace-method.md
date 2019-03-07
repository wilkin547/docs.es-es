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
ms.openlocfilehash: b102f49a642d2bcd62e7f75a8dd0b9ab782ad674
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491352"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="3cc77-102">ISymUnmanagedWriter::UsingNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="3cc77-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="3cc77-103">Especifica que se utiliza el nombre completo del espacio de nombres determinado dentro del ámbito léxico abierto actualmente.</span><span class="sxs-lookup"><span data-stu-id="3cc77-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="3cc77-104">El espacio de nombres se utilizará en todos los ámbitos que se heredan del ámbito abierto actualmente.</span><span class="sxs-lookup"><span data-stu-id="3cc77-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="3cc77-105">Al cerrar el ámbito actual, también se detendrá el uso del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3cc77-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cc77-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cc77-106">Syntax</span></span>  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cc77-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3cc77-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="3cc77-108">[in] Un puntero al nombre completo del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3cc77-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3cc77-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3cc77-109">Return Value</span></span>  
 <span data-ttu-id="3cc77-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="3cc77-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cc77-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cc77-111">Requirements</span></span>  
 <span data-ttu-id="3cc77-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3cc77-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cc77-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cc77-113">See also</span></span>
- [<span data-ttu-id="3cc77-114">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3cc77-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
