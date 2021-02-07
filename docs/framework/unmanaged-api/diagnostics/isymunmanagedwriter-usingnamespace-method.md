---
description: 'Más información acerca de: ISymUnmanagedWriter:: Usingnamespace ((método)'
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
ms.openlocfilehash: e7d56cded125aac6154d4315c587f58f946a9a82
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761959"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="09b29-103">ISymUnmanagedWriter::UsingNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="09b29-103">ISymUnmanagedWriter::UsingNamespace Method</span></span>

<span data-ttu-id="09b29-104">Especifica que el nombre completo del espacio de nombres especificado se está usando en el ámbito léxico abierto actualmente.</span><span class="sxs-lookup"><span data-stu-id="09b29-104">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="09b29-105">El espacio de nombres se usará en todos los ámbitos que heredan del ámbito abierto actualmente.</span><span class="sxs-lookup"><span data-stu-id="09b29-105">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="09b29-106">Al cerrar el ámbito actual, también se detendrá el uso del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="09b29-106">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09b29-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09b29-107">Syntax</span></span>  
  
```cpp  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09b29-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09b29-108">Parameters</span></span>  

 `fullName`  
 <span data-ttu-id="09b29-109">de Puntero al nombre completo del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="09b29-109">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09b29-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="09b29-110">Return Value</span></span>  

 <span data-ttu-id="09b29-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="09b29-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09b29-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09b29-112">Requirements</span></span>  

 <span data-ttu-id="09b29-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="09b29-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09b29-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="09b29-114">See also</span></span>

- [<span data-ttu-id="09b29-115">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09b29-115">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
