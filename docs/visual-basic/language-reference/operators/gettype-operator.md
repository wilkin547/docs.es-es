---
title: GetType (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 2e3e05973f2ef72fef5e429bc98cc58b4b21f2c2
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592154"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="f541e-102">GetType (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f541e-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="f541e-103">Devuelve un objeto <xref:System.Type> para el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="f541e-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="f541e-104">El objeto <xref:System.Type> proporciona información sobre el tipo, como sus propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="f541e-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f541e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f541e-105">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="f541e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f541e-106">Parameters</span></span>  
  
|<span data-ttu-id="f541e-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="f541e-107">Parameter</span></span>|<span data-ttu-id="f541e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f541e-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="f541e-109">Nombre del tipo del que se desea obtener información.</span><span class="sxs-lookup"><span data-stu-id="f541e-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f541e-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f541e-110">Remarks</span></span>  
 <span data-ttu-id="f541e-111">El operador `GetType` devuelve el objeto <xref:System.Type> para el `typename`especificado.</span><span class="sxs-lookup"><span data-stu-id="f541e-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="f541e-112">Puede pasar el nombre de cualquier tipo definido en `typename`.</span><span class="sxs-lookup"><span data-stu-id="f541e-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="f541e-113">Entre estas estructuras se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="f541e-113">This includes the following:</span></span>  
  
- <span data-ttu-id="f541e-114">Cualquier tipo de datos Visual Basic, como `Boolean` o `Date`.</span><span class="sxs-lookup"><span data-stu-id="f541e-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="f541e-115">Cualquier .NET Framework clase, estructura, módulo o interfaz, como <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f541e-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="f541e-116">Cualquier clase, estructura, módulo o interfaz definida por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f541e-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="f541e-117">Cualquier matriz definida por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f541e-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="f541e-118">Cualquier delegado definido por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f541e-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="f541e-119">Cualquier enumeración definida por Visual Basic, la .NET Framework o la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f541e-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="f541e-120">Si desea obtener el objeto de tipo de una variable de objeto, use el método <xref:System.Type.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f541e-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="f541e-121">El operador `GetType` puede ser útil en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="f541e-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="f541e-122">Debe tener acceso a los metadatos de un tipo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f541e-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="f541e-123">El objeto <xref:System.Type> proporciona metadatos, como los miembros de tipo e información de implementación.</span><span class="sxs-lookup"><span data-stu-id="f541e-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="f541e-124">Necesita esto, por ejemplo, para reflejarse en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f541e-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="f541e-125">Para obtener más información, consulta <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f541e-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="f541e-126">Desea comparar dos referencias de objeto para ver si hacen referencia a instancias del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="f541e-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="f541e-127">Si lo hacen, `GetType` devuelve referencias al mismo objeto <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="f541e-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f541e-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f541e-128">Example</span></span>  
 <span data-ttu-id="f541e-129">En los siguientes ejemplos se muestra el operador de `GetType` en uso.</span><span class="sxs-lookup"><span data-stu-id="f541e-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="f541e-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="f541e-130">See also</span></span>

- [<span data-ttu-id="f541e-131">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f541e-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f541e-132">Operadores enumerados por funcionalidad</span><span class="sxs-lookup"><span data-stu-id="f541e-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f541e-133">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="f541e-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
