---
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
ms.openlocfilehash: 12475b1ac8a1a81e565aa689eac2ae1a9b55e73a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438287"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="42355-102">ISymUnmanagedWriter2::DefineGlobalVariable2 (Método)</span><span class="sxs-lookup"><span data-stu-id="42355-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>
<span data-ttu-id="42355-103">Define una única variable global.</span><span class="sxs-lookup"><span data-stu-id="42355-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42355-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42355-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="42355-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42355-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="42355-106">de Nombre de la variable global.</span><span class="sxs-lookup"><span data-stu-id="42355-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="42355-107">de Atributos de la variable global.</span><span class="sxs-lookup"><span data-stu-id="42355-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="42355-108">de Símbolo (token) de metadatos de la firma.</span><span class="sxs-lookup"><span data-stu-id="42355-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="42355-109">de Tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="42355-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="42355-110">de Primera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="42355-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="42355-111">de Segunda dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="42355-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="42355-112">de Tercera dirección de la especificación de parámetro.</span><span class="sxs-lookup"><span data-stu-id="42355-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42355-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="42355-113">Return Value</span></span>  
 <span data-ttu-id="42355-114">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="42355-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42355-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42355-115">Requirements</span></span>  
 <span data-ttu-id="42355-116">**Encabezado:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="42355-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42355-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="42355-117">See also</span></span>

- [<span data-ttu-id="42355-118">ISymUnmanagedWriter2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="42355-118">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="42355-119">DefineGlobalVariable (método)</span><span class="sxs-lookup"><span data-stu-id="42355-119">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
