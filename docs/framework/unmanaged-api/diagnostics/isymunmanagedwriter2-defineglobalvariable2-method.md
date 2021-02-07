---
description: 'Más información acerca de: ISymUnmanagedWriter2::D efineGlobalVariable2 (método)'
title: ISymUnmanagedWriter2::DefineGlobalVariable2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
ms.openlocfilehash: 9a33ff8d452419ff103c9f4402620bd28196ae54
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761907"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="aa024-103">ISymUnmanagedWriter2::DefineGlobalVariable2 (Método)</span><span class="sxs-lookup"><span data-stu-id="aa024-103">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>

<span data-ttu-id="aa024-104">Define una única variable global.</span><span class="sxs-lookup"><span data-stu-id="aa024-104">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa024-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa024-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa024-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa024-106">Parameters</span></span>  

 `name`  
 <span data-ttu-id="aa024-107">de Nombre de la variable global.</span><span class="sxs-lookup"><span data-stu-id="aa024-107">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="aa024-108">de Atributos de la variable global.</span><span class="sxs-lookup"><span data-stu-id="aa024-108">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="aa024-109">de Símbolo (token) de metadatos de la firma.</span><span class="sxs-lookup"><span data-stu-id="aa024-109">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="aa024-110">de Tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="aa024-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="aa024-111">de Primera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="aa024-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="aa024-112">de Segunda dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="aa024-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="aa024-113">de Tercera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="aa024-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa024-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aa024-114">Return Value</span></span>  

 <span data-ttu-id="aa024-115">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="aa024-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa024-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa024-116">Requirements</span></span>  

 <span data-ttu-id="aa024-117">**Encabezado:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="aa024-117">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa024-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa024-118">See also</span></span>

- [<span data-ttu-id="aa024-119">ISymUnmanagedWriter2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa024-119">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="aa024-120">Método DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="aa024-120">DefineGlobalVariable Method</span></span>](isymunmanagedwriter-defineglobalvariable-method.md)
