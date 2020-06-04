---
title: La expresión tiene el tipo '<typename>' que es un tipo restringido y no se puede utilizar para obtener acceso a miembros heredados de 'Object' o 'ValueType'
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 0eb30488312cc7519f39a6b819aea15489f2f70a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409525"
---
# <a name="expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a><span data-ttu-id="491bd-102">La expresión tiene el tipo '\<typename>' que es un tipo restringido y no se puede utilizar para obtener acceso a miembros heredados de 'Object' o 'ValueType'</span><span class="sxs-lookup"><span data-stu-id="491bd-102">Expression has the type '\<typename>' which is a restricted type and cannot be used to access members inherited from 'Object' or 'ValueType'</span></span>
<span data-ttu-id="491bd-103">Una expresión se evalúa como un tipo al que el Common Language Runtime (CLR) no puede aplicar la conversión boxing, pero tiene acceso a un miembro que requiere la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="491bd-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="491bd-104">La*conversión boxing* hace referencia al procesamiento necesario para convertir un tipo a `Object` o, en ocasiones, a <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="491bd-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="491bd-105">En el Common Language Runtime no se pueden Box determinados tipos de estructura, por ejemplo <xref:System.ArgIterator> , <xref:System.RuntimeArgumentHandle> y <xref:System.TypedReference> .</span><span class="sxs-lookup"><span data-stu-id="491bd-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="491bd-106">Esta expresión intenta utilizar el tipo restringido para llamar a un método heredado de <xref:System.Object> o <xref:System.ValueType> , como <xref:System.Object.GetHashCode%2A> o <xref:System.Object.ToString%2A> .</span><span class="sxs-lookup"><span data-stu-id="491bd-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="491bd-107">Para obtener acceso a este método, Visual Basic ha intentado realizar una conversión boxing implícita que produce este error.</span><span class="sxs-lookup"><span data-stu-id="491bd-107">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="491bd-108">**Identificador de error:** BC31393</span><span class="sxs-lookup"><span data-stu-id="491bd-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="491bd-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="491bd-109">To correct this error</span></span>  
  
1. <span data-ttu-id="491bd-110">Localice la expresión que se evalúa en el tipo mencionado.</span><span class="sxs-lookup"><span data-stu-id="491bd-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2. <span data-ttu-id="491bd-111">Busque la parte de la instrucción que intenta llamar al método heredado de <xref:System.Object> o <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="491bd-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3. <span data-ttu-id="491bd-112">Vuelva a escribir la instrucción para evitar la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="491bd-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="491bd-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="491bd-113">See also</span></span>

- [<span data-ttu-id="491bd-114">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="491bd-114">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
