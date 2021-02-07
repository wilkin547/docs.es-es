---
description: 'Más información sobre: ISymENCUnmanagedMethod:: GetFileNameFromOffset ((método)'
title: ISymENCUnmanagedMethod::GetFileNameFromOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetFileNameFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetFileNameFromOffset
helpviewer_keywords:
- GetFileNameFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetFileNameFromOffset method [.NET Framework debugging]
ms.assetid: 00e2e194-12f5-436e-a997-2b9d3e844d4f
topic_type:
- apiref
ms.openlocfilehash: 1322e55f115958a2f4b2634dfa25eff127167d54
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738005"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="8ec49-103">ISymENCUnmanagedMethod::GetFileNameFromOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="8ec49-103">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>

<span data-ttu-id="8ec49-104">Obtiene el nombre de archivo de la línea asociada a un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="8ec49-104">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ec49-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ec49-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ec49-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8ec49-106">Parameters</span></span>  

 `dwOffset`  
 <span data-ttu-id="8ec49-107">de Un `ULONG32` que contiene el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="8ec49-107">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="8ec49-108">de `ULONG32` Que indica el tamaño del `szName` búfer.</span><span class="sxs-lookup"><span data-stu-id="8ec49-108">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="8ec49-109">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener los nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="8ec49-109">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="8ec49-110">enuncia Búfer que contiene los nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="8ec49-110">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ec49-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8ec49-111">Return Value</span></span>  

 <span data-ttu-id="8ec49-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8ec49-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ec49-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ec49-113">Requirements</span></span>  

 <span data-ttu-id="8ec49-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8ec49-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ec49-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ec49-115">See also</span></span>

- [<span data-ttu-id="8ec49-116">ISymENCUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8ec49-116">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
