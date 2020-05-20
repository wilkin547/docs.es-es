---
title: ISymUnmanagedScope::GetLocalCount (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
ms.openlocfilehash: 9ffba23e3821c48c9b0708e4b6b617db4ddc5959
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83611268"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="66941-102">ISymUnmanagedScope::GetLocalCount (Método)</span><span class="sxs-lookup"><span data-stu-id="66941-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="66941-103">Obtiene un recuento de las variables locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="66941-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66941-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66941-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66941-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66941-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="66941-106">enuncia Un puntero a un `ULONG32` que recibe el recuento de variables locales.</span><span class="sxs-lookup"><span data-stu-id="66941-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66941-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="66941-107">Return Value</span></span>  
 <span data-ttu-id="66941-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="66941-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66941-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66941-109">Requirements</span></span>  
 <span data-ttu-id="66941-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="66941-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66941-111">Consulta también</span><span class="sxs-lookup"><span data-stu-id="66941-111">See also</span></span>

- [<span data-ttu-id="66941-112">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66941-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
