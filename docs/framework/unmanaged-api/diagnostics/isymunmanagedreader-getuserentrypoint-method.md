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
ms.openlocfilehash: d465f830fa73016c3cf3f7df3a4a4d0c42bc0980
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615506"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="9eb3f-102">ISymUnmanagedReader::GetUserEntryPoint (Método)</span><span class="sxs-lookup"><span data-stu-id="9eb3f-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="9eb3f-103">Devuelve el método que se especificó como punto de entrada del usuario para el módulo, si existe.</span><span class="sxs-lookup"><span data-stu-id="9eb3f-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="9eb3f-104">Por ejemplo, este método podría ser el método Main del usuario en lugar de códigos auxiliares generados por el compilador antes del método Main.</span><span class="sxs-lookup"><span data-stu-id="9eb3f-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eb3f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9eb3f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9eb3f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9eb3f-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="9eb3f-107">enuncia Puntero a una variable que recibe el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="9eb3f-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9eb3f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9eb3f-108">Return Value</span></span>  
 <span data-ttu-id="9eb3f-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="9eb3f-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9eb3f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9eb3f-110">Requirements</span></span>  
 <span data-ttu-id="9eb3f-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="9eb3f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eb3f-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="9eb3f-112">See also</span></span>

- [<span data-ttu-id="9eb3f-113">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9eb3f-113">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
