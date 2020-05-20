---
title: ISymUnmanagedVariable::GetAttributes (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAttributes
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAttributes
helpviewer_keywords:
- GetAttributes method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAttributes method [.NET Framework debugging]
ms.assetid: 80f168af-a6a6-4c8f-b9e6-8a82dc834ed5
topic_type:
- apiref
ms.openlocfilehash: 29869abdd39f61c6c9cb51d6b2be50fa462c5b70
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615259"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="9f66f-102">ISymUnmanagedVariable::GetAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="9f66f-102">ISymUnmanagedVariable::GetAttributes Method</span></span>
<span data-ttu-id="9f66f-103">Obtiene las marcas de atributo para esta variable.</span><span class="sxs-lookup"><span data-stu-id="9f66f-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f66f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f66f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f66f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9f66f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="9f66f-106">enuncia Un puntero a un `ULONG32` que recibe los atributos.</span><span class="sxs-lookup"><span data-stu-id="9f66f-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="9f66f-107">El valor devuelto será uno de los valores definidos en la enumeración [corsymvarflag (](corsymvarflag-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="9f66f-107">The returned value will be one of the values defined in the [CorSymVarFlag](corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f66f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9f66f-108">Return Value</span></span>  
 <span data-ttu-id="9f66f-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="9f66f-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f66f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f66f-110">Requirements</span></span>  
 <span data-ttu-id="9f66f-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="9f66f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f66f-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="9f66f-112">See also</span></span>

- [<span data-ttu-id="9f66f-113">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9f66f-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
