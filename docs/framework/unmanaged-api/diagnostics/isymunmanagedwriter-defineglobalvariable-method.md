---
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
ms.openlocfilehash: 94d1aa5bba87e8ca11b58bdf89a697e1ccf500b1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428024"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="e7288-102">ISymUnmanagedWriter::DefineGlobalVariable (Método)</span><span class="sxs-lookup"><span data-stu-id="e7288-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>
<span data-ttu-id="e7288-103">Define una única variable global.</span><span class="sxs-lookup"><span data-stu-id="e7288-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7288-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7288-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e7288-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e7288-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="e7288-106">de Puntero a un `WCHAR` que define el nombre de la variable global.</span><span class="sxs-lookup"><span data-stu-id="e7288-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="e7288-107">de Atributos de la variable global.</span><span class="sxs-lookup"><span data-stu-id="e7288-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="e7288-108">de `ULONG32` que indica el tamaño, en caracteres, del búfer de `signature`.</span><span class="sxs-lookup"><span data-stu-id="e7288-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="e7288-109">de Firma de la variable global.</span><span class="sxs-lookup"><span data-stu-id="e7288-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="e7288-110">de Tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="e7288-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="e7288-111">de Primera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="e7288-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="e7288-112">de Segunda dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="e7288-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="e7288-113">de Tercera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="e7288-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7288-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e7288-114">Return Value</span></span>  
 <span data-ttu-id="e7288-115">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e7288-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7288-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7288-116">Requirements</span></span>  
 <span data-ttu-id="e7288-117">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e7288-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7288-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7288-118">See also</span></span>

- [<span data-ttu-id="e7288-119">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7288-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="e7288-120">DefineLocalVariable (método)</span><span class="sxs-lookup"><span data-stu-id="e7288-120">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
- [<span data-ttu-id="e7288-121">DefineGlobalVariable2 (método)</span><span class="sxs-lookup"><span data-stu-id="e7288-121">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)
