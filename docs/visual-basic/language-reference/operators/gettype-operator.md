---
title: GetType (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 34ab192814583db5cdc0d0183c73cc22b8633e9c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840327"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="d224f-102">GetType (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d224f-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="d224f-103">Devuelve un <xref:System.Type> objeto para el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="d224f-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="d224f-104">La <xref:System.Type> objeto proporciona información sobre el tipo como sus propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="d224f-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d224f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d224f-105">Syntax</span></span>  
  
```  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="d224f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d224f-106">Parameters</span></span>  
  
|<span data-ttu-id="d224f-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="d224f-107">Parameter</span></span>|<span data-ttu-id="d224f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d224f-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="d224f-109">El nombre del tipo para el que se desea obtener información.</span><span class="sxs-lookup"><span data-stu-id="d224f-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d224f-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d224f-110">Remarks</span></span>  
 <span data-ttu-id="d224f-111">El `GetType` operador devuelve el <xref:System.Type> objeto para el elemento especificado `typename`.</span><span class="sxs-lookup"><span data-stu-id="d224f-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="d224f-112">Puede pasar el nombre de cualquier tipo definido en `typename`.</span><span class="sxs-lookup"><span data-stu-id="d224f-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="d224f-113">Entre estas estructuras se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d224f-113">This includes the following:</span></span>  
  
-   <span data-ttu-id="d224f-114">Escriba los datos de Visual Basic, como `Boolean` o `Date`.</span><span class="sxs-lookup"><span data-stu-id="d224f-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
-   <span data-ttu-id="d224f-115">Cualquier clase, estructura, módulo o interfaz, .NET Framework, como <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d224f-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="d224f-116">Cualquier clase, estructura, módulo o interfaz definida por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d224f-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
-   <span data-ttu-id="d224f-117">Cualquier matriz definida por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d224f-117">Any array defined by your application.</span></span>  
  
-   <span data-ttu-id="d224f-118">Cualquier delegado definido por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d224f-118">Any delegate defined by your application.</span></span>  
  
-   <span data-ttu-id="d224f-119">Cualquiera de las enumeraciones definida por la aplicación, .NET Framework o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d224f-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="d224f-120">Si desea obtener el objeto de tipo de una variable de objeto, utilice el <xref:System.Type.GetType%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="d224f-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="d224f-121">El `GetType` operador puede ser útil en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="d224f-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
-   <span data-ttu-id="d224f-122">Debe tener acceso a los metadatos para un tipo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d224f-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="d224f-123">La <xref:System.Type> objeto proporciona los metadatos como miembros de tipo y la información de implementación.</span><span class="sxs-lookup"><span data-stu-id="d224f-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="d224f-124">Necesita esto, por ejemplo, para reflejar a través de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d224f-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="d224f-125">Para obtener más información, consulta <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d224f-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="d224f-126">Desea comparar dos referencias de objeto para ver si hacen referencia a las instancias del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="d224f-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="d224f-127">Si lo hacen, `GetType` devuelve referencias al mismo <xref:System.Type> objeto.</span><span class="sxs-lookup"><span data-stu-id="d224f-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d224f-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d224f-128">Example</span></span>  
 <span data-ttu-id="d224f-129">Los ejemplos siguientes muestran el `GetType` operador en uso.</span><span class="sxs-lookup"><span data-stu-id="d224f-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="d224f-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="d224f-130">See also</span></span>

- [<span data-ttu-id="d224f-131">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d224f-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="d224f-132">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="d224f-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="d224f-133">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="d224f-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
