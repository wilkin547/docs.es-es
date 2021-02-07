---
description: 'Más información acerca de: ISymUnmanagedWriter::D método efineGlobalVariable'
title: ISymUnmanagedWriter::DefineGlobalVariable (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineGlobalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type:
- apiref
ms.openlocfilehash: 70dccfed054a9ac79baf3f28683edc9a14d3cdf7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762388"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="87d7c-103">ISymUnmanagedWriter::DefineGlobalVariable (Método)</span><span class="sxs-lookup"><span data-stu-id="87d7c-103">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>

<span data-ttu-id="87d7c-104">Define una única variable global.</span><span class="sxs-lookup"><span data-stu-id="87d7c-104">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87d7c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87d7c-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87d7c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="87d7c-106">Parameters</span></span>  

 `name`  
 <span data-ttu-id="87d7c-107">de Puntero a `WCHAR` que define el nombre de la variable global.</span><span class="sxs-lookup"><span data-stu-id="87d7c-107">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="87d7c-108">de Atributos de la variable global.</span><span class="sxs-lookup"><span data-stu-id="87d7c-108">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="87d7c-109">de `ULONG32` Que indica el tamaño, en caracteres, del `signature` búfer.</span><span class="sxs-lookup"><span data-stu-id="87d7c-109">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="87d7c-110">de Firma de la variable global.</span><span class="sxs-lookup"><span data-stu-id="87d7c-110">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="87d7c-111">de Tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="87d7c-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="87d7c-112">de Primera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="87d7c-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="87d7c-113">de Segunda dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="87d7c-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="87d7c-114">de Tercera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="87d7c-114">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87d7c-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="87d7c-115">Return Value</span></span>  

 <span data-ttu-id="87d7c-116">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="87d7c-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87d7c-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87d7c-117">Requirements</span></span>  

 <span data-ttu-id="87d7c-118">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="87d7c-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d7c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="87d7c-119">See also</span></span>

- [<span data-ttu-id="87d7c-120">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="87d7c-120">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="87d7c-121">Método DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="87d7c-121">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
- [<span data-ttu-id="87d7c-122">Método DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="87d7c-122">DefineGlobalVariable2 Method</span></span>](isymunmanagedwriter2-defineglobalvariable2-method.md)
