---
description: 'Más información acerca de: interfaz Isymunmanagedwriter4 ('
title: ISymUnmanagedWriter4 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: 3814d7e2728f28d224a4e9a6d99f699f220e8a4d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761686"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="4398f-103">ISymUnmanagedWriter4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4398f-103">ISymUnmanagedWriter4 Interface</span></span>

<span data-ttu-id="4398f-104">Interfaz Isymunmanagedwriter4 (.</span><span class="sxs-lookup"><span data-stu-id="4398f-104">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4398f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4398f-105">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="4398f-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="4398f-106">Methods</span></span>  

 <span data-ttu-id="4398f-107">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="4398f-107">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="4398f-108">Método</span><span class="sxs-lookup"><span data-stu-id="4398f-108">Method</span></span>|<span data-ttu-id="4398f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4398f-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4398f-110">Método GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="4398f-110">GetDebugInfoWithPadding Method</span></span>](isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="4398f-111">Funciona igual que el [método GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md) , salvo que la cadena de ruta de acceso se rellena con ceros después del carácter nulo de terminación para convertir los datos de cadena en un tamaño fijo de `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="4398f-111">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="4398f-112">El relleno solo se proporciona si la longitud de la cadena de ruta de acceso es menor que `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="4398f-112">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="4398f-113">Esto facilita la escritura de herramientas que diferencian los archivos PE.</span><span class="sxs-lookup"><span data-stu-id="4398f-113">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4398f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4398f-114">Requirements</span></span>  

 <span data-ttu-id="4398f-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="4398f-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4398f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4398f-116">See also</span></span>

- [<span data-ttu-id="4398f-117">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="4398f-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="4398f-118">ISymUnmanagedWriter3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4398f-118">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
