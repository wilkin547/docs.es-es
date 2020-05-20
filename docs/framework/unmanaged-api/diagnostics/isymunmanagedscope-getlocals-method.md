---
title: ISymUnmanagedScope::GetLocals (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
ms.openlocfilehash: 0acd31d85504688427cace0222a657885035c537
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615389"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="26c6b-102">ISymUnmanagedScope::GetLocals (Método)</span><span class="sxs-lookup"><span data-stu-id="26c6b-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="26c6b-103">Obtiene las variables locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="26c6b-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26c6b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26c6b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26c6b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="26c6b-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="26c6b-106">de `ULONG32`Que indica el tamaño de la `locals` matriz.</span><span class="sxs-lookup"><span data-stu-id="26c6b-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="26c6b-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener las variables locales.</span><span class="sxs-lookup"><span data-stu-id="26c6b-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="26c6b-108">enuncia La matriz que recibe las variables locales.</span><span class="sxs-lookup"><span data-stu-id="26c6b-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26c6b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="26c6b-109">Return Value</span></span>  
 <span data-ttu-id="26c6b-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="26c6b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26c6b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26c6b-111">Requirements</span></span>  
 <span data-ttu-id="26c6b-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="26c6b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c6b-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="26c6b-113">See also</span></span>

- [<span data-ttu-id="26c6b-114">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="26c6b-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
