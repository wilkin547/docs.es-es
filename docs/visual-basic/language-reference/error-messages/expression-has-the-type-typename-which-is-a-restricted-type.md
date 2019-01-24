---
title: Expresión tiene el tipo &#39; &lt;typename&gt; &#39; que es un tipo restringido y no se puede usar para tener acceso a miembros heredados de &#39;objeto&#39; o &#39;ValueType&#39;
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: d44b9a29f0848508d8cd814e857d9b01819ce7ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535962"
---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a><span data-ttu-id="f5857-102">Expresión tiene el tipo &#39; &lt;typename&gt; &#39; que es un tipo restringido y no se puede usar para tener acceso a miembros heredados de &#39;objeto&#39; o &#39;ValueType&#39;</span><span class="sxs-lookup"><span data-stu-id="f5857-102">Expression has the type &#39;&lt;typename&gt;&#39; which is a restricted type and cannot be used to access members inherited from &#39;Object&#39; or &#39;ValueType&#39;</span></span>
<span data-ttu-id="f5857-103">Una expresión se evalúa como un tipo que no se puede realizar la conversión boxing por common language runtime (CLR), pero tiene acceso a un miembro que requiere la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="f5857-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="f5857-104">La*conversión boxing* hace referencia al procesamiento necesario para convertir un tipo a `Object` o, en ocasiones, a <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="f5857-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="f5857-105">Common language runtime no puede encerrar ciertos tipos de estructura, por ejemplo <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, y <xref:System.TypedReference>.</span><span class="sxs-lookup"><span data-stu-id="f5857-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="f5857-106">Esta expresión intenta utilizar el tipo restringido para llamar a un método heredado de <xref:System.Object> o <xref:System.ValueType>, tales como <xref:System.Object.GetHashCode%2A> o <xref:System.Object.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="f5857-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="f5857-107">Para obtener acceso a este método, Visual Basic ha intentado una conversión boxing implícita que produce este error.</span><span class="sxs-lookup"><span data-stu-id="f5857-107">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="f5857-108">**Identificador de error:** BC31393</span><span class="sxs-lookup"><span data-stu-id="f5857-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f5857-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f5857-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="f5857-110">Localice la expresión que se evalúa en el tipo mencionado.</span><span class="sxs-lookup"><span data-stu-id="f5857-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2.  <span data-ttu-id="f5857-111">Busque la parte de la instrucción que intenta llamar al método se hereda de <xref:System.Object> o <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="f5857-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3.  <span data-ttu-id="f5857-112">Reescriba la instrucción para evitar la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="f5857-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5857-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5857-113">See also</span></span>
- [<span data-ttu-id="f5857-114">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="f5857-114">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
