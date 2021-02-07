---
description: 'Más información acerca de: ISymUnmanagedVariable:: GetName (método)'
title: ISymUnmanagedVariable::GetName (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type:
- apiref
ms.openlocfilehash: 88d8cf4c81200a30e2a102b63af2817fef2b50c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762791"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="a08f5-103">ISymUnmanagedVariable::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="a08f5-103">ISymUnmanagedVariable::GetName Method</span></span>

<span data-ttu-id="a08f5-104">Obtiene el nombre de esta variable.</span><span class="sxs-lookup"><span data-stu-id="a08f5-104">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a08f5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a08f5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a08f5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a08f5-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="a08f5-107">de Longitud del búfer al que apunta el `pcchName` parámetro.</span><span class="sxs-lookup"><span data-stu-id="a08f5-107">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a08f5-108">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el nombre, incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="a08f5-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="a08f5-109">enuncia Búfer que almacena el nombre.</span><span class="sxs-lookup"><span data-stu-id="a08f5-109">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a08f5-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a08f5-110">Return Value</span></span>  

 <span data-ttu-id="a08f5-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a08f5-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a08f5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a08f5-112">Requirements</span></span>  

 <span data-ttu-id="a08f5-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="a08f5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a08f5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a08f5-114">See also</span></span>

- [<span data-ttu-id="a08f5-115">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a08f5-115">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
