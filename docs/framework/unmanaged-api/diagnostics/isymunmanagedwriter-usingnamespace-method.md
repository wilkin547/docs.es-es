---
title: "ISymUnmanagedWriter::UsingNamespace (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.UsingNamespace
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b9bfd5ca0c22a9b4da1acb1f93b29150beba865a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="68431-102">ISymUnmanagedWriter::UsingNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="68431-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="68431-103">Especifica que el nombre completo del espacio de nombres especificado se utiliza dentro del ámbito léxico abierto.</span><span class="sxs-lookup"><span data-stu-id="68431-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="68431-104">El espacio de nombres se utilizará en todos los ámbitos que heredan del ámbito abierto actualmente.</span><span class="sxs-lookup"><span data-stu-id="68431-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="68431-105">Cerrar el ámbito actual, también se detendrá el uso del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="68431-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68431-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68431-106">Syntax</span></span>  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="68431-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="68431-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="68431-108">[in] Un puntero al nombre completo del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="68431-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68431-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="68431-109">Return Value</span></span>  
 <span data-ttu-id="68431-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="68431-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68431-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="68431-111">Requirements</span></span>  
 <span data-ttu-id="68431-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="68431-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68431-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="68431-113">See Also</span></span>  
 [<span data-ttu-id="68431-114">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="68431-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
