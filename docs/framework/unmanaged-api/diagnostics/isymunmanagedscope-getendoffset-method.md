---
title: ISymUnmanagedScope::GetEndOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
ms.openlocfilehash: 4d6bd239a15bd196f840007af120cb062499f4c9
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614856"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="58f71-102">ISymUnmanagedScope::GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="58f71-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="58f71-103">Obtiene el desplazamiento final para este ámbito.</span><span class="sxs-lookup"><span data-stu-id="58f71-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58f71-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58f71-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58f71-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58f71-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="58f71-106">enuncia Un puntero a un `ULONG32` que recibe el desplazamiento final.</span><span class="sxs-lookup"><span data-stu-id="58f71-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58f71-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="58f71-107">Return Value</span></span>  
 <span data-ttu-id="58f71-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="58f71-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58f71-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58f71-109">Requirements</span></span>  
 <span data-ttu-id="58f71-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="58f71-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58f71-111">Consulta también</span><span class="sxs-lookup"><span data-stu-id="58f71-111">See also</span></span>

- [<span data-ttu-id="58f71-112">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="58f71-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="58f71-113">Método GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="58f71-113">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)
