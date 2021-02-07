---
description: 'Más información sobre: ISymUnmanagedVariable:: GetAttributes (método)'
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
ms.openlocfilehash: 0adaeaf512f129f92b7f15cdba375395a0a81855
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762843"
---
# <a name="isymunmanagedvariablegetattributes-method"></a><span data-ttu-id="02557-103">ISymUnmanagedVariable::GetAttributes (Método)</span><span class="sxs-lookup"><span data-stu-id="02557-103">ISymUnmanagedVariable::GetAttributes Method</span></span>

<span data-ttu-id="02557-104">Obtiene las marcas de atributo para esta variable.</span><span class="sxs-lookup"><span data-stu-id="02557-104">Gets the attribute flags for this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02557-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02557-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAttributes(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02557-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="02557-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="02557-107">enuncia Un puntero a un `ULONG32` que recibe los atributos.</span><span class="sxs-lookup"><span data-stu-id="02557-107">[out] A pointer to a `ULONG32` that receives the attributes.</span></span> <span data-ttu-id="02557-108">El valor devuelto será uno de los valores definidos en la enumeración [corsymvarflag (](corsymvarflag-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="02557-108">The returned value will be one of the values defined in the [CorSymVarFlag](corsymvarflag-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02557-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="02557-109">Return Value</span></span>  

 <span data-ttu-id="02557-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="02557-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02557-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02557-111">Requirements</span></span>  

 <span data-ttu-id="02557-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="02557-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02557-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="02557-113">See also</span></span>

- [<span data-ttu-id="02557-114">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="02557-114">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
