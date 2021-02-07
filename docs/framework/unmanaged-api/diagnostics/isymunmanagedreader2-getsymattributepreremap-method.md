---
description: 'Más información sobre: ISymUnmanagedReader2:: Getsymattributepreremap ((método)'
title: ISymUnmanagedReader2::GetSymAttributePreRemap (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetSymAttributePreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type:
- apiref
ms.openlocfilehash: 843a3d2d2a568fdff83d2e416fff426daad14645
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763636"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a><span data-ttu-id="262ca-103">ISymUnmanagedReader2::GetSymAttributePreRemap (Método)</span><span class="sxs-lookup"><span data-stu-id="262ca-103">ISymUnmanagedReader2::GetSymAttributePreRemap Method</span></span>

<span data-ttu-id="262ca-104">Obtiene un atributo personalizado basado en su nombre.</span><span class="sxs-lookup"><span data-stu-id="262ca-104">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="262ca-105">A diferencia de los atributos personalizados de metadatos, estos atributos se guardan en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="262ca-105">Unlike metadata custom attributes, these attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="262ca-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="262ca-106">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="262ca-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="262ca-107">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="262ca-108">de Token de metadatos del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="262ca-108">[in] The metadata token of the parent.</span></span>  
  
 `name`  
 <span data-ttu-id="262ca-109">de Un puntero a un `WCHAR` que contiene el nombre.</span><span class="sxs-lookup"><span data-stu-id="262ca-109">[in] A pointer to a `WCHAR` that contains the name.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="262ca-110">de `ULONG32` Que indica el tamaño de la `buffer` matriz.</span><span class="sxs-lookup"><span data-stu-id="262ca-110">[in] A `ULONG32` that indicates the size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="262ca-111">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los bytes de atributo.</span><span class="sxs-lookup"><span data-stu-id="262ca-111">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the attribute bytes.</span></span>  
  
 `buffer`  
 <span data-ttu-id="262ca-112">enuncia Puntero al búfer que recibe los bytes de atributo.</span><span class="sxs-lookup"><span data-stu-id="262ca-112">[out] A pointer to the buffer that receives the attribute bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="262ca-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="262ca-113">Return Value</span></span>  

 <span data-ttu-id="262ca-114">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="262ca-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="262ca-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="262ca-115">Requirements</span></span>  

 <span data-ttu-id="262ca-116">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="262ca-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="262ca-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="262ca-117">See also</span></span>

- [<span data-ttu-id="262ca-118">ISymUnmanagedReader2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="262ca-118">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
