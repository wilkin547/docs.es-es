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
ms.openlocfilehash: 6404252f2c1eb14f0cd723451beb82b4c65960fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683490"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="59458-102">ISymUnmanagedWriter::UsingNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="59458-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>

<span data-ttu-id="59458-103">Especifica que el nombre completo del espacio de nombres especificado se está usando en el ámbito léxico abierto actualmente.</span><span class="sxs-lookup"><span data-stu-id="59458-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="59458-104">El espacio de nombres se usará en todos los ámbitos que heredan del ámbito abierto actualmente.</span><span class="sxs-lookup"><span data-stu-id="59458-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="59458-105">Al cerrar el ámbito actual, también se detendrá el uso del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="59458-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59458-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59458-106">Syntax</span></span>  
  
```cpp  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59458-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="59458-107">Parameters</span></span>  

 `fullName`  
 <span data-ttu-id="59458-108">de Puntero al nombre completo del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="59458-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59458-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="59458-109">Return Value</span></span>  

 <span data-ttu-id="59458-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="59458-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59458-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59458-111">Requirements</span></span>  

 <span data-ttu-id="59458-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="59458-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59458-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59458-113">See also</span></span>

- [<span data-ttu-id="59458-114">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="59458-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
