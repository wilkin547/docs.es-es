---
title: "Aplicar la conversión boxing a tipos que aceptan valores NULL (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5ce063a70ced98fd8b99b4b46d704e08ddc96e10
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="boxing-nullable-types-c-programming-guide"></a><span data-ttu-id="047fc-102">Aplicar la conversión boxing a tipos que aceptan valores NULL (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="047fc-102">Boxing Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="047fc-103">La conversión boxing solo se aplica a los objetos basados en tipos que aceptan valores NULL si el valor del objeto no es NULL.</span><span class="sxs-lookup"><span data-stu-id="047fc-103">Objects based on nullable types are only boxed if the object is non-null.</span></span> <span data-ttu-id="047fc-104">Si <xref:System.Nullable%601.HasValue%2A> es `false`, la referencia de objeto se asigna a `null` en lugar de aplicar la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="047fc-104">If <xref:System.Nullable%601.HasValue%2A> is `false`, the object reference is assigned to `null` instead of boxing.</span></span> <span data-ttu-id="047fc-105">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="047fc-105">For example:</span></span>  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 <span data-ttu-id="047fc-106">Si el objeto no es NULL (si <xref:System.Nullable%601.HasValue%2A> es `true`), tiene lugar la conversión boxing, pero solo se aplica al tipo subyacente en el que se basa el objeto que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="047fc-106">If the object is non-null -- if <xref:System.Nullable%601.HasValue%2A> is `true` -- then boxing occurs, but only the underlying type that the nullable object is based on is boxed.</span></span> <span data-ttu-id="047fc-107">La conversión boxing de un tipo de valor no NULL que acepta valores NULL se aplica al propio tipo de valor, no al objeto <xref:System.Nullable%601?displayProperty=fullName> que ajusta el tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="047fc-107">Boxing a non-null nullable value type boxes the value type itself, not the <xref:System.Nullable%601?displayProperty=fullName> that wraps the value type.</span></span> <span data-ttu-id="047fc-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="047fc-108">For example:</span></span>  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 <span data-ttu-id="047fc-109">Los dos objetos a los que se aplica la conversión boxing son idénticos a aquellos creados aplicando la conversión boxing a tipos que no aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="047fc-109">The two boxed objects are identical to those created by boxing non-nullable types.</span></span> <span data-ttu-id="047fc-110">Además, al igual que los tipos sin conversión boxing que aceptan valores NULL, se les puede aplicar la conversión unboxing en los tipos que aceptan valores NULL, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="047fc-110">And, just like non-nullable boxed types, they can be unboxed into nullable types, as in the following example:</span></span>  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a><span data-ttu-id="047fc-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="047fc-111">Remarks</span></span>  
 <span data-ttu-id="047fc-112">El comportamiento de los tipos que aceptan valores NULL cuando se aplica la conversión boxing proporciona dos ventajas:</span><span class="sxs-lookup"><span data-stu-id="047fc-112">The behavior of nullable types when boxed provides two advantages:</span></span>  
  
1.  <span data-ttu-id="047fc-113">Se comprueba si los objetos que aceptan valores NULL y sus homólogos a los que se aplica la conversión boxing tienen valores NULL:</span><span class="sxs-lookup"><span data-stu-id="047fc-113">Nullable objects and their boxed counterpart can be tested for null:</span></span>  
  
    ```csharp  
    bool? b = null;  
    object boxedB = b;  
    if (b == null)  
    {  
      // True.  
    }  
    if (boxedB == null)  
    {  
      // Also true.  
    }  
    ```  
  
2.  <span data-ttu-id="047fc-114">Los tipos que aceptan valores NULL y a los que se aplica la conversión boxing admiten la función del tipo subyacente:</span><span class="sxs-lookup"><span data-stu-id="047fc-114">Boxed nullable types fully support the functionality of the underlying type:</span></span>  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="047fc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="047fc-115">See Also</span></span>  
 <span data-ttu-id="047fc-116">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="047fc-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="047fc-117">[Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="047fc-117">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="047fc-118">Cómo: Identificar tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="047fc-118">How to: Identify a Nullable Type</span></span>](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)

