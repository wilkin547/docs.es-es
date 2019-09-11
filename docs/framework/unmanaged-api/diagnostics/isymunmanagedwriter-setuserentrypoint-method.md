---
title: ISymUnmanagedWriter::SetUserEntryPoint (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11dc050e2fe16a64db4ac95bb1386e2d90535e81
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895028"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="2158b-102">ISymUnmanagedWriter::SetUserEntryPoint (Método)</span><span class="sxs-lookup"><span data-stu-id="2158b-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="2158b-103">Especifica el método definido por el usuario que es el punto de entrada de este módulo.</span><span class="sxs-lookup"><span data-stu-id="2158b-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="2158b-104">Por ejemplo, este punto de entrada podría ser el método Main del usuario en lugar de los códigos auxiliares generados por el compilador antes de Main.</span><span class="sxs-lookup"><span data-stu-id="2158b-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2158b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2158b-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2158b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2158b-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="2158b-107">de Símbolo (token) de metadatos para el método que es el punto de entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="2158b-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2158b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2158b-108">Return Value</span></span>  
 <span data-ttu-id="2158b-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="2158b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2158b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2158b-110">Requirements</span></span>  
 <span data-ttu-id="2158b-111">**Encabezado**: CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="2158b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2158b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2158b-112">See also</span></span>

- [<span data-ttu-id="2158b-113">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2158b-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
