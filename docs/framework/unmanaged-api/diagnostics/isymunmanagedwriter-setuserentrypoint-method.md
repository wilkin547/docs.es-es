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
ms.openlocfilehash: a1c3506758221c3a2b578d93488a4377c1b86a21
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683503"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="4c823-102">ISymUnmanagedWriter::SetUserEntryPoint (Método)</span><span class="sxs-lookup"><span data-stu-id="4c823-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>

<span data-ttu-id="4c823-103">Especifica el método definido por el usuario que es el punto de entrada de este módulo.</span><span class="sxs-lookup"><span data-stu-id="4c823-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="4c823-104">Por ejemplo, este punto de entrada podría ser el método Main del usuario en lugar de los códigos auxiliares generados por el compilador antes de Main.</span><span class="sxs-lookup"><span data-stu-id="4c823-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c823-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c823-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c823-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4c823-106">Parameters</span></span>  

 `entryMethod`  
 <span data-ttu-id="4c823-107">de Símbolo (token) de metadatos para el método que es el punto de entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="4c823-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c823-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4c823-108">Return Value</span></span>  

 <span data-ttu-id="4c823-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="4c823-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c823-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4c823-110">Requirements</span></span>  

 <span data-ttu-id="4c823-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="4c823-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c823-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c823-112">See also</span></span>

- [<span data-ttu-id="4c823-113">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4c823-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
