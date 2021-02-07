---
description: 'Más información acerca de: operador GetType (Visual Basic)'
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 15fe9c28997aa01527f23c0cc8fdbb0fe6cc53f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665996"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="4bb9f-103">GetType (Operador, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4bb9f-103">GetType Operator (Visual Basic)</span></span>

<span data-ttu-id="4bb9f-104">Devuelve un <xref:System.Type> objeto para el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="4bb9f-104">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="4bb9f-105">El <xref:System.Type> objeto proporciona información sobre el tipo, como sus propiedades, métodos y eventos.</span><span class="sxs-lookup"><span data-stu-id="4bb9f-105">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bb9f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bb9f-106">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bb9f-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4bb9f-107">Parameters</span></span>  
  
|<span data-ttu-id="4bb9f-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="4bb9f-108">Parameter</span></span>|<span data-ttu-id="4bb9f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bb9f-109">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="4bb9f-110">Nombre del tipo del que se desea obtener información.</span><span class="sxs-lookup"><span data-stu-id="4bb9f-110">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bb9f-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4bb9f-111">Remarks</span></span>  

 <span data-ttu-id="4bb9f-112">El `GetType` operador devuelve el <xref:System.Type> objeto para el especificado `typename` .</span><span class="sxs-lookup"><span data-stu-id="4bb9f-112">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="4bb9f-113">Puede pasar el nombre de cualquier tipo definido en `typename` .</span><span class="sxs-lookup"><span data-stu-id="4bb9f-113">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="4bb9f-114">Entre estas estructuras se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="4bb9f-114">This includes the following:</span></span>  
  
- <span data-ttu-id="4bb9f-115">Cualquier tipo de datos Visual Basic, como `Boolean` o `Date` .</span><span class="sxs-lookup"><span data-stu-id="4bb9f-115">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="4bb9f-116">Cualquier .NET Framework clase, estructura, módulo o interfaz, como <xref:System.ArgumentException?displayProperty=nameWithType> o <xref:System.Double?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4bb9f-116">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="4bb9f-117">Cualquier clase, estructura, módulo o interfaz definida por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4bb9f-117">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="4bb9f-118">Cualquier matriz definida por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4bb9f-118">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="4bb9f-119">Cualquier delegado definido por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4bb9f-119">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="4bb9f-120">Cualquier enumeración definida por Visual Basic, la .NET Framework o la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4bb9f-120">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="4bb9f-121">Si desea obtener el objeto de tipo de una variable de objeto, use el <xref:System.Type.GetType%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="4bb9f-121">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="4bb9f-122">El `GetType` operador puede ser útil en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="4bb9f-122">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="4bb9f-123">Debe tener acceso a los metadatos de un tipo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4bb9f-123">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="4bb9f-124">El <xref:System.Type> objeto proporciona metadatos, como los miembros de tipo e información de implementación.</span><span class="sxs-lookup"><span data-stu-id="4bb9f-124">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="4bb9f-125">Necesita esto, por ejemplo, para reflejarse en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4bb9f-125">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="4bb9f-126">Para obtener más información, vea <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4bb9f-126">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="4bb9f-127">Desea comparar dos referencias de objeto para ver si hacen referencia a instancias del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="4bb9f-127">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="4bb9f-128">Si lo hacen, `GetType` devuelve referencias al mismo <xref:System.Type> objeto.</span><span class="sxs-lookup"><span data-stu-id="4bb9f-128">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bb9f-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4bb9f-129">Example</span></span>  

 <span data-ttu-id="4bb9f-130">En los siguientes ejemplos se muestra el `GetType` operador en uso.</span><span class="sxs-lookup"><span data-stu-id="4bb9f-130">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="4bb9f-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bb9f-131">See also</span></span>

- [<span data-ttu-id="4bb9f-132">Prioridad de operador en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4bb9f-132">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="4bb9f-133">Lista de operadores según funcionalidad</span><span class="sxs-lookup"><span data-stu-id="4bb9f-133">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="4bb9f-134">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="4bb9f-134">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
