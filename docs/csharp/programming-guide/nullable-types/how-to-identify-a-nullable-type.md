---
title: 'Cómo: Identificar tipos que aceptan valores NULL (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: f3ac4ebd77fc92a133eb326919d5ba55264ced97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333188"
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a><span data-ttu-id="dfb4f-102">Cómo: Identificar tipos que aceptan valores NULL (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="dfb4f-102">How to: Identify a Nullable Type (C# Programming Guide)</span></span>
<span data-ttu-id="dfb4f-103">Puede usar el operador [typeof](../../../csharp/language-reference/keywords/typeof.md) de C# para crear un objeto <xref:System.Type> que represente un tipo que acepta valores NULL:</span><span class="sxs-lookup"><span data-stu-id="dfb4f-103">You can use the C# [typeof](../../../csharp/language-reference/keywords/typeof.md) operator to create a <xref:System.Type> object that represents a Nullable type:</span></span>  
  
```  
System.Type type = typeof(int?);  
```  
  
 <span data-ttu-id="dfb4f-104">También puede usar las clases y métodos del espacio de nombres <xref:System.Reflection> para generar objetos <xref:System.Type> que representen tipos que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="dfb4f-104">You can also use the classes and methods of the <xref:System.Reflection> namespace to generate <xref:System.Type> objects that represent Nullable types.</span></span> <span data-ttu-id="dfb4f-105">En cambio, si intenta obtener información de tipo de las variables que aceptan valores NULL en tiempo de ejecución mediante el método <xref:System.Object.GetType%2A> o el operador `is`, el resultado será un objeto <xref:System.Type> que representa el tipo subyacente y no el propio tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="dfb4f-105">However, if you try to obtain type information from Nullable variables at runtime by using the <xref:System.Object.GetType%2A> method or the `is` operator, the result is a <xref:System.Type> object that represents the underlying type, not the Nullable type itself.</span></span>  
  
 <span data-ttu-id="dfb4f-106">La llamada a `GetType` en un tipo que acepta valores NULL origina que se ejecute una operación de conversión boxing cuando el tipo se convierte implícitamente en <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="dfb4f-106">Calling `GetType` on a Nullable type causes a boxing operation to be performed when the type is implicitly converted to <xref:System.Object>.</span></span> <span data-ttu-id="dfb4f-107">Por consiguiente, <xref:System.Object.GetType%2A> siempre devuelve un objeto <xref:System.Type> que representa el tipo subyacente y no el tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="dfb4f-107">Therefore <xref:System.Object.GetType%2A> always returns a <xref:System.Type> object that represents the underlying type, not the Nullable type.</span></span>  
  
```  
int? i = 5;  
Type t = i.GetType();  
Console.WriteLine(t.FullName); //"System.Int32"  
```  
  
 <span data-ttu-id="dfb4f-108">El operador [is](../../../csharp/language-reference/keywords/is.md) de C# funciona también en el tipo subyacente de un tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="dfb4f-108">The C# [is](../../../csharp/language-reference/keywords/is.md) operator also operates on a Nullable's underlying type.</span></span> <span data-ttu-id="dfb4f-109">Por tanto, no puede usar `is` para determinar si una variable es un tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="dfb4f-109">Therefore you cannot use `is` to determine whether a variable is a Nullable type.</span></span> <span data-ttu-id="dfb4f-110">En el ejemplo siguiente se muestra que el operador `is` trata una variable \<int> que acepta valores NULL como un valor int.</span><span class="sxs-lookup"><span data-stu-id="dfb4f-110">The following example shows that the `is` operator treats a Nullable\<int> variable as an int.</span></span>  
  
```  
static void Main(string[] args)  
{  
  int? i = 5;  
  if (i is int) // true  
    //…  
}  
```  
  
## <a name="example"></a><span data-ttu-id="dfb4f-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dfb4f-111">Example</span></span>  
 <span data-ttu-id="dfb4f-112">Use el código siguiente para determinar si un objeto <xref:System.Type> representa un tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="dfb4f-112">Use the following code to determine whether a <xref:System.Type> object represents a Nullable type.</span></span> <span data-ttu-id="dfb4f-113">Recuerde que este código siempre devuelve false si el objeto `Type` se devuelve de una llamada a <xref:System.Object.GetType%2A>, como se ha explicado anteriormente en este mismo tema.</span><span class="sxs-lookup"><span data-stu-id="dfb4f-113">Remember that this code always returns false if the `Type` object was returned from a call to <xref:System.Object.GetType%2A>, as explained earlier in this topic.</span></span>  
  
```  
if (type.IsGenericType && type.GetGenericTypeDefinition() == typeof(Nullable<>)) {…}  
```  
  
## <a name="see-also"></a><span data-ttu-id="dfb4f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfb4f-114">See Also</span></span>  
 [<span data-ttu-id="dfb4f-115">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="dfb4f-115">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="dfb4f-116">Aplicar la conversión boxing a tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="dfb4f-116">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)
