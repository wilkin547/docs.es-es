---
description: 'Más información acerca de: ISymUnmanagedConstant:: GetName (método)'
title: ISymUnmanagedConstant::GetName (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
ms.openlocfilehash: 57531711ed60c9e35e749a3cb1f1ba5d5c48ca66
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689825"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="0eb2b-103">ISymUnmanagedConstant::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="0eb2b-103">ISymUnmanagedConstant::GetName Method</span></span>

<span data-ttu-id="0eb2b-104">Obtiene el nombre de la constante.</span><span class="sxs-lookup"><span data-stu-id="0eb2b-104">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eb2b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0eb2b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0eb2b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0eb2b-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="0eb2b-107">de Longitud del búfer al que apunta el `szName` parámetro.</span><span class="sxs-lookup"><span data-stu-id="0eb2b-107">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0eb2b-108">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el nombre, incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="0eb2b-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="0eb2b-109">enuncia Búfer que almacena el nombre.</span><span class="sxs-lookup"><span data-stu-id="0eb2b-109">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0eb2b-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0eb2b-110">Return Value</span></span>  

 <span data-ttu-id="0eb2b-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="0eb2b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eb2b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0eb2b-112">Requirements</span></span>  

 <span data-ttu-id="0eb2b-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0eb2b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb2b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0eb2b-114">See also</span></span>

- [<span data-ttu-id="0eb2b-115">ISymUnmanagedConstant (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0eb2b-115">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="0eb2b-116">GetSignature (Método)</span><span class="sxs-lookup"><span data-stu-id="0eb2b-116">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="0eb2b-117">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="0eb2b-117">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)
