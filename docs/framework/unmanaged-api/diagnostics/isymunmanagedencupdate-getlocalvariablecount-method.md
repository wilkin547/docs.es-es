---
description: 'Más información sobre: ISymUnmanagedENCUpdate:: GetLocalVariableCount ((método)'
title: ISymUnmanagedENCUpdate::GetLocalVariableCount (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
ms.openlocfilehash: ab75ba0b0dda5722aebdbdc8b9a242cc90b0ac11
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790157"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="751bf-103">ISymUnmanagedENCUpdate::GetLocalVariableCount (Método)</span><span class="sxs-lookup"><span data-stu-id="751bf-103">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>

<span data-ttu-id="751bf-104">Obtiene el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="751bf-104">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="751bf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="751bf-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
## <a name="parameters"></a><span data-ttu-id="751bf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="751bf-106">Parameters</span></span>  

 `mdMethodToken`  
 <span data-ttu-id="751bf-107">de Símbolo (token) de metadatos de los métodos.</span><span class="sxs-lookup"><span data-stu-id="751bf-107">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="751bf-108">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="751bf-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="751bf-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="751bf-109">Return Value</span></span>  

 <span data-ttu-id="751bf-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="751bf-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="751bf-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="751bf-111">Requirements</span></span>  

 <span data-ttu-id="751bf-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="751bf-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="751bf-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="751bf-113">See also</span></span>

- [<span data-ttu-id="751bf-114">ISymUnmanagedENCUpdate (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="751bf-114">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
