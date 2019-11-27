---
title: ISymUnmanagedVariable (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
ms.openlocfilehash: ee57ba14f048032e2cd9d0129089743c0f0304bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445977"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="71c43-102">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="71c43-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="71c43-103">Representa una variable, como un parámetro, una variable local o un campo.</span><span class="sxs-lookup"><span data-stu-id="71c43-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="71c43-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="71c43-104">Methods</span></span>  
  
|<span data-ttu-id="71c43-105">Método</span><span class="sxs-lookup"><span data-stu-id="71c43-105">Method</span></span>|<span data-ttu-id="71c43-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="71c43-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="71c43-107">GetAddressField1 (método)</span><span class="sxs-lookup"><span data-stu-id="71c43-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="71c43-108">Obtiene el primer campo de dirección para esta variable.</span><span class="sxs-lookup"><span data-stu-id="71c43-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="71c43-109">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="71c43-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="71c43-110">GetAddressField2 (método)</span><span class="sxs-lookup"><span data-stu-id="71c43-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="71c43-111">Obtiene el segundo campo de dirección para esta variable.</span><span class="sxs-lookup"><span data-stu-id="71c43-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="71c43-112">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="71c43-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="71c43-113">GetAddressField3 (método)</span><span class="sxs-lookup"><span data-stu-id="71c43-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="71c43-114">Obtiene el tercer campo de dirección para esta variable.</span><span class="sxs-lookup"><span data-stu-id="71c43-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="71c43-115">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="71c43-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="71c43-116">GetAddressKind (método)</span><span class="sxs-lookup"><span data-stu-id="71c43-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="71c43-117">Obtiene el tipo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="71c43-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="71c43-118">GetAttributes (método)</span><span class="sxs-lookup"><span data-stu-id="71c43-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="71c43-119">Obtiene las marcas de atributo para esta variable.</span><span class="sxs-lookup"><span data-stu-id="71c43-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="71c43-120">GetEndOffset (método)</span><span class="sxs-lookup"><span data-stu-id="71c43-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="71c43-121">Obtiene el desplazamiento final de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="71c43-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="71c43-122">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="71c43-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="71c43-123">Obtiene el nombre de esta variable.</span><span class="sxs-lookup"><span data-stu-id="71c43-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="71c43-124">GetSignature (método)</span><span class="sxs-lookup"><span data-stu-id="71c43-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="71c43-125">Obtiene la firma de esta variable.</span><span class="sxs-lookup"><span data-stu-id="71c43-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="71c43-126">GetStartOffset (método)</span><span class="sxs-lookup"><span data-stu-id="71c43-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="71c43-127">Obtiene el desplazamiento inicial de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="71c43-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71c43-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71c43-128">Requirements</span></span>  
 <span data-ttu-id="71c43-129">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="71c43-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71c43-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="71c43-130">See also</span></span>

- [<span data-ttu-id="71c43-131">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="71c43-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
