---
description: 'Más información sobre: ISymUnmanagedScope2:: Getconstants ((método)'
title: ISymUnmanagedScope2::GetConstants (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
ms.openlocfilehash: 025bb9ddd0501f2309b2c0a3f7af20eb961604cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763220"
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="8683e-103">ISymUnmanagedScope2::GetConstants (Método)</span><span class="sxs-lookup"><span data-stu-id="8683e-103">ISymUnmanagedScope2::GetConstants Method</span></span>

<span data-ttu-id="8683e-104">Obtiene las constantes locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="8683e-104">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8683e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8683e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*
             constants[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8683e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8683e-106">Parameters</span></span>  

 `cConstants`  
 <span data-ttu-id="8683e-107">de Longitud del búfer al que apunta el `pcConstants` parámetro.</span><span class="sxs-lookup"><span data-stu-id="8683e-107">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="8683e-108">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener las constantes.</span><span class="sxs-lookup"><span data-stu-id="8683e-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="8683e-109">enuncia Búfer que almacena las constantes.</span><span class="sxs-lookup"><span data-stu-id="8683e-109">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8683e-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8683e-110">Return Value</span></span>  

 <span data-ttu-id="8683e-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8683e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8683e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8683e-112">Requirements</span></span>  

 <span data-ttu-id="8683e-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8683e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8683e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8683e-114">See also</span></span>

- [<span data-ttu-id="8683e-115">ISymUnmanagedScope2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8683e-115">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
