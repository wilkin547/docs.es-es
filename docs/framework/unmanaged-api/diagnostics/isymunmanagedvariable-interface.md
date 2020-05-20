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
ms.openlocfilehash: d05d4451e8fb75829b22e0a1b9c9afcb0607eb8b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610176"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="7d0a9-102">ISymUnmanagedVariable (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d0a9-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="7d0a9-103">Representa una variable, como un parámetro, una variable local o un campo.</span><span class="sxs-lookup"><span data-stu-id="7d0a9-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7d0a9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7d0a9-104">Methods</span></span>  
  
|<span data-ttu-id="7d0a9-105">Método</span><span class="sxs-lookup"><span data-stu-id="7d0a9-105">Method</span></span>|<span data-ttu-id="7d0a9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d0a9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7d0a9-107">Método GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="7d0a9-107">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="7d0a9-108">Obtiene el primer campo de dirección para esta variable.</span><span class="sxs-lookup"><span data-stu-id="7d0a9-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="7d0a9-109">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="7d0a9-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="7d0a9-110">Método GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="7d0a9-110">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="7d0a9-111">Obtiene el segundo campo de dirección para esta variable.</span><span class="sxs-lookup"><span data-stu-id="7d0a9-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="7d0a9-112">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="7d0a9-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="7d0a9-113">Método GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="7d0a9-113">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="7d0a9-114">Obtiene el tercer campo de dirección para esta variable.</span><span class="sxs-lookup"><span data-stu-id="7d0a9-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="7d0a9-115">Su significado depende del tipo de dirección.</span><span class="sxs-lookup"><span data-stu-id="7d0a9-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="7d0a9-116">Método GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="7d0a9-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="7d0a9-117">Obtiene el tipo de dirección de esta variable.</span><span class="sxs-lookup"><span data-stu-id="7d0a9-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="7d0a9-118">Método GetAttributes</span><span class="sxs-lookup"><span data-stu-id="7d0a9-118">GetAttributes Method</span></span>](isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="7d0a9-119">Obtiene las marcas de atributo para esta variable.</span><span class="sxs-lookup"><span data-stu-id="7d0a9-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="7d0a9-120">GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="7d0a9-120">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="7d0a9-121">Obtiene el desplazamiento final de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="7d0a9-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="7d0a9-122">Método GetName</span><span class="sxs-lookup"><span data-stu-id="7d0a9-122">GetName Method</span></span>](isymunmanagedvariable-getname-method.md)|<span data-ttu-id="7d0a9-123">Obtiene el nombre de esta variable.</span><span class="sxs-lookup"><span data-stu-id="7d0a9-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="7d0a9-124">GetSignature (Método)</span><span class="sxs-lookup"><span data-stu-id="7d0a9-124">GetSignature Method</span></span>](isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="7d0a9-125">Obtiene la firma de esta variable.</span><span class="sxs-lookup"><span data-stu-id="7d0a9-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="7d0a9-126">Método GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="7d0a9-126">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="7d0a9-127">Obtiene el desplazamiento inicial de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="7d0a9-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d0a9-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d0a9-128">Requirements</span></span>  
 <span data-ttu-id="7d0a9-129">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7d0a9-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d0a9-130">Consulta también</span><span class="sxs-lookup"><span data-stu-id="7d0a9-130">See also</span></span>

- [<span data-ttu-id="7d0a9-131">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="7d0a9-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
