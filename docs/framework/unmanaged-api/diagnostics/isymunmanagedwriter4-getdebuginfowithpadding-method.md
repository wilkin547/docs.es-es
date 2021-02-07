---
description: 'Más información sobre: Isymunmanagedwriter4 (:: Getdebuginfowithpadding ((método)'
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding (Método)
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
ms.openlocfilehash: f5a2026a4ddf12b741b670097e31260e68f33c7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761712"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="287bd-103">ISymUnmanagedWriter4::GetDebugInfoWithPadding (Método)</span><span class="sxs-lookup"><span data-stu-id="287bd-103">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>

<span data-ttu-id="287bd-104">Funciona igual que el [método GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md) , salvo que la cadena de ruta de acceso se rellena con ceros después del carácter nulo de terminación para convertir los datos de cadena en un tamaño fijo de `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="287bd-104">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="287bd-105">El relleno solo se proporciona si la longitud de la cadena de ruta de acceso es menor que `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="287bd-105">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="287bd-106">Esto facilita la escritura de herramientas que diferencian los archivos PE.</span><span class="sxs-lookup"><span data-stu-id="287bd-106">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="287bd-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="287bd-107">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="287bd-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="287bd-108">Parameters</span></span>  
  
|<span data-ttu-id="287bd-109">Parámetro</span><span class="sxs-lookup"><span data-stu-id="287bd-109">Parameter</span></span>|<span data-ttu-id="287bd-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="287bd-110">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="287bd-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="287bd-111">Return Value</span></span>  

 <span data-ttu-id="287bd-112">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="287bd-112">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="287bd-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="287bd-113">Requirements</span></span>  

 <span data-ttu-id="287bd-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="287bd-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="287bd-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="287bd-115">See also</span></span>

- [<span data-ttu-id="287bd-116">ISymUnmanagedWriter4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="287bd-116">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)
