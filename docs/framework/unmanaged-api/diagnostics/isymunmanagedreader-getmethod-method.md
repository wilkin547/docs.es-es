---
description: 'Más información acerca de: ISymUnmanagedReader:: GetMethod (método)'
title: ISymUnmanagedReader::GetMethod (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedReader interface [.NET Framework debugging]
- ISymUnmanagedReader::GetMethod method [.NET Framework debugging]
ms.assetid: ae6cfb29-bc2c-4606-af86-1d32ebd31020
topic_type:
- apiref
ms.openlocfilehash: 7c0bb65840a3bc1c9450ad29fa8438cdb0377a16
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689500"
---
# <a name="isymunmanagedreadergetmethod-method"></a><span data-ttu-id="81fde-103">ISymUnmanagedReader::GetMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="81fde-103">ISymUnmanagedReader::GetMethod Method</span></span>

<span data-ttu-id="81fde-104">Obtiene un método del lector de símbolos, dado un token de método.</span><span class="sxs-lookup"><span data-stu-id="81fde-104">Gets a symbol reader method, given a method token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81fde-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81fde-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod (  
    [in]  mdMethodDef  token,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81fde-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81fde-106">Parameters</span></span>  

 `token`  
 <span data-ttu-id="81fde-107">de Token del método.</span><span class="sxs-lookup"><span data-stu-id="81fde-107">[in] The method token.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="81fde-108">enuncia Puntero a la interfaz devuelta.</span><span class="sxs-lookup"><span data-stu-id="81fde-108">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81fde-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="81fde-109">Return Value</span></span>  

 <span data-ttu-id="81fde-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="81fde-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81fde-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81fde-111">Requirements</span></span>  

 <span data-ttu-id="81fde-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="81fde-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81fde-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="81fde-113">See also</span></span>

- [<span data-ttu-id="81fde-114">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="81fde-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
