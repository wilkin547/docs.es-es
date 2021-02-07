---
description: 'Más información sobre: ISymUnmanagedMethod:: GetSequencePointCount ((método)'
title: ISymUnmanagedMethod::GetSequencePointCount (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePointCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePointCount
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePointCount method [.NET Framework debugging]
- GetSequencePointCount method [.NET Framework debugging]
ms.assetid: 836133e8-6108-4b9b-b0a9-bce4e08dccda
topic_type:
- apiref
ms.openlocfilehash: 6e0341ddc151454de8764a47a92556ab1925bfa1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710014"
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="b9c2c-103">ISymUnmanagedMethod::GetSequencePointCount (Método)</span><span class="sxs-lookup"><span data-stu-id="b9c2c-103">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>

<span data-ttu-id="b9c2c-104">Obtiene el recuento de puntos de secuencia dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="b9c2c-104">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9c2c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9c2c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9c2c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b9c2c-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="b9c2c-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="b9c2c-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9c2c-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b9c2c-108">Return Value</span></span>  

 <span data-ttu-id="b9c2c-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="b9c2c-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9c2c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9c2c-110">Requirements</span></span>  

 <span data-ttu-id="b9c2c-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b9c2c-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9c2c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9c2c-112">See also</span></span>

- [<span data-ttu-id="b9c2c-113">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9c2c-113">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
