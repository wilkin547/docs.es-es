---
title: GetType (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 581f576222eb149aede841a5da7a0e5f38c77b58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603852"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="1f5fa-102">GetType (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f5fa-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="1f5fa-103">Devuelve un <xref:System.Type> objeto para el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="1f5fa-104">La <xref:System.Type> objeto proporciona información sobre el tipo como sus propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f5fa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f5fa-105">Syntax</span></span>  
  
```  
GetType(typename)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f5fa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1f5fa-106">Parameters</span></span>  
  
|<span data-ttu-id="1f5fa-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="1f5fa-107">Parameter</span></span>|<span data-ttu-id="1f5fa-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f5fa-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="1f5fa-109">El nombre del tipo para el que se desea obtener información.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f5fa-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1f5fa-110">Remarks</span></span>  
 <span data-ttu-id="1f5fa-111">El `GetType` operador devuelve el <xref:System.Type> objeto para el elemento especificado `typename`.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="1f5fa-112">Puede pasar el nombre de cualquier tipo definido en `typename`.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="1f5fa-113">Entre estas estructuras se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="1f5fa-113">This includes the following:</span></span>  
  
-   <span data-ttu-id="1f5fa-114">Tipo de los datos de Visual Basic, como `Boolean` o `Date`.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
-   <span data-ttu-id="1f5fa-115">Cualquier clase, estructura, módulo o interfaz, .NET Framework como <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="1f5fa-116">Cualquier clase, estructura, módulo o interfaz definida por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
-   <span data-ttu-id="1f5fa-117">Cualquier matriz definida por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-117">Any array defined by your application.</span></span>  
  
-   <span data-ttu-id="1f5fa-118">Cualquier delegado definido por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-118">Any delegate defined by your application.</span></span>  
  
-   <span data-ttu-id="1f5fa-119">Cualquiera de las enumeraciones definida por Visual Basic, .NET Framework o la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="1f5fa-120">Si desea obtener el objeto de tipo de una variable de objeto, utilice el <xref:System.Type.GetType%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="1f5fa-121">La `GetType` puede ser útil en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="1f5fa-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
-   <span data-ttu-id="1f5fa-122">Debe tener acceso a los metadatos para un tipo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="1f5fa-123">La <xref:System.Type> objeto que proporciona metadatos como miembros de tipo e información de implementación.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="1f5fa-124">Lo necesita, por ejemplo, para reflejar en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="1f5fa-125">Para obtener más información, consulta <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="1f5fa-126">Desea comparar dos referencias de objeto para ver si hacen referencia a instancias del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="1f5fa-127">Si es así, `GetType` devuelve referencias a los mismos <xref:System.Type> objeto.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f5fa-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f5fa-128">Example</span></span>  
 <span data-ttu-id="1f5fa-129">Los ejemplos siguientes muestran el `GetType` operador en uso.</span><span class="sxs-lookup"><span data-stu-id="1f5fa-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/gettype-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1f5fa-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f5fa-130">See Also</span></span>  
 [<span data-ttu-id="1f5fa-131">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f5fa-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="1f5fa-132">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="1f5fa-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="1f5fa-133">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="1f5fa-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
