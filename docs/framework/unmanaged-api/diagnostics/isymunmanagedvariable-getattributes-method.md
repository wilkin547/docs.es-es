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
ms.openlocfilehash: 1142dbb83693f6104ba6e22e174ce02fb92997a6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726904"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="ec71c-102">ISymUnmanagedVariable::GetAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="ec71c-102">ISymUnmanagedVariable::GetAttributes Method</span></span>

<span data-ttu-id="ec71c-103">Obtiene las marcas de atributo para esta variable.</span><span class="sxs-lookup"><span data-stu-id="ec71c-103">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec71c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec71c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec71c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec71c-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="ec71c-106">enuncia Un puntero a un `ULONG32` que recibe los atributos.</span><span class="sxs-lookup"><span data-stu-id="ec71c-106">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="ec71c-107">El valor devuelto será uno de los valores definidos en la enumeración [corsymvarflag (](corsymvarflag-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ec71c-107">The returned value will be one of the values defined in the [CorSymVarFlag](corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec71c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ec71c-108">Return Value</span></span>  

 <span data-ttu-id="ec71c-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="ec71c-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec71c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec71c-110">Requirements</span></span>  

 <span data-ttu-id="ec71c-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="ec71c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec71c-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec71c-112">See also</span></span>

- [<span data-ttu-id="ec71c-113">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec71c-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
