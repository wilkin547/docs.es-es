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
ms.openlocfilehash: 8b51a9dc3a968c6bd2f5f9b149f13f88dc6a1e05
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614752"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="d395f-102">ISymUnmanagedWriter::SetUserEntryPoint (Método)</span><span class="sxs-lookup"><span data-stu-id="d395f-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="d395f-103">Especifica el método definido por el usuario que es el punto de entrada de este módulo.</span><span class="sxs-lookup"><span data-stu-id="d395f-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="d395f-104">Por ejemplo, este punto de entrada podría ser el método Main del usuario en lugar de los códigos auxiliares generados por el compilador antes de Main.</span><span class="sxs-lookup"><span data-stu-id="d395f-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d395f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d395f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d395f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d395f-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="d395f-107">de Símbolo (token) de metadatos para el método que es el punto de entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="d395f-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d395f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d395f-108">Return Value</span></span>  
 <span data-ttu-id="d395f-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d395f-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d395f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d395f-110">Requirements</span></span>  
 <span data-ttu-id="d395f-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d395f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d395f-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="d395f-112">See also</span></span>

- [<span data-ttu-id="d395f-113">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d395f-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
