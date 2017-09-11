---
title: "Cómo: Saber las diferencias entre pasar a un método un struct y una referencia a clase (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- structs [C#], passing as method parameter
- passing parameters [C#], structs vs. classes
- methods [C#], passing classes vs. structs
ms.assetid: 9c1313a6-32a8-4ea7-a59f-450f66af628b
caps.latest.revision: 25
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
ms.openlocfilehash: 1a4508c8765ac678fd371180cb0c3ece3e1d9a44
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-know-the-difference-between-passing-a-struct-and-passing-a-class-reference-to-a-method-c-programming-guide"></a><span data-ttu-id="9b8f8-102">Cómo: Saber las diferencias entre pasar a un método un struct y una referencia a clase (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9b8f8-102">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method (C# Programming Guide)</span></span>
<span data-ttu-id="9b8f8-103">En el ejemplo siguiente se muestra cómo pasar un [struct](../../../csharp/language-reference/keywords/struct.md) a un método es diferente de pasar una instancia de [clase](../../../csharp/language-reference/keywords/class.md) a un método.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-103">The following example demonstrates how passing a [struct](../../../csharp/language-reference/keywords/struct.md) to a method differs from passing a [class](../../../csharp/language-reference/keywords/class.md) instance to a method.</span></span> <span data-ttu-id="9b8f8-104">En el ejemplo, los dos argumentos (struct e instancia de clase) se pasan mediante valor, y ambos métodos cambian el valor de un campo del argumento.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-104">In the example, both of the arguments (struct and class instance) are passed by value, and both methods change the value of one field of the argument.</span></span> <span data-ttu-id="9b8f8-105">En cambio, los resultados de los dos métodos no son los mismos porque lo que se pasa cuando pasa un struct difiere de lo que se pasa cuando pasa una instancia de una clase.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-105">However, the results of the two methods are not the same because what is passed when you pass a struct differs from what is passed when you pass an instance of a class.</span></span>  
  
 <span data-ttu-id="9b8f8-106">Como un struct es un [tipo de valor](../../../csharp/language-reference/keywords/value-types.md), cuando [pasa un struct mediante valor](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md) a un método, el método recibe y funciona en una copia del argumento struct.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-106">Because a struct is a [value type](../../../csharp/language-reference/keywords/value-types.md), when you [pass a struct by value](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md) to a method, the method receives and operates on a copy of the struct argument.</span></span> <span data-ttu-id="9b8f8-107">El método no tiene acceso al struct original en el método de llamada y, por lo tanto, no puede cambiarlo de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-107">The method has no access to the original struct in the calling method and therefore can't change it in any way.</span></span> <span data-ttu-id="9b8f8-108">El método solo puede cambiar la copia.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-108">The method can change only the copy.</span></span>  
  
 <span data-ttu-id="9b8f8-109">Una instancia de clase es un [tipo de referencia](../../../csharp/language-reference/keywords/reference-types.md), no un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-109">A class instance is a [reference type](../../../csharp/language-reference/keywords/reference-types.md), not a value type.</span></span> <span data-ttu-id="9b8f8-110">Cuando [un tipo de referencia se pasa mediante valor](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) a un método, el método recibe una copia de la referencia a la instancia de clase.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-110">When [a reference type is passed by value](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) to a method, the method receives a copy of the reference to the class instance.</span></span> <span data-ttu-id="9b8f8-111">Es decir, el método recibe una copia de la dirección de la instancia, no una copia de la propia instancia.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-111">That is, the method receives a copy of the address of the instance, not a copy of the instance itself.</span></span> <span data-ttu-id="9b8f8-112">La instancia de clase en el método de llamada tiene una dirección, el parámetro en el método que se ha llamado tiene una copia de la dirección, y ambas direcciones hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-112">The class instance in the calling method has an address, the parameter in the called method has a copy of the address, and both addresses refer to the same object.</span></span> <span data-ttu-id="9b8f8-113">Como el parámetro solo contiene una copia de la dirección, el método al que se ha llamado no puede cambiar la dirección de la instancia de clase en el método de llamada.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-113">Because the parameter contains only a copy of the address, the called method cannot change the address of the class instance in the calling method.</span></span> <span data-ttu-id="9b8f8-114">En cambio, el método al que se ha llamado puede usar la dirección para tener acceso a los miembros de clase que la dirección original y la copia hacen referencia.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-114">However, the called method can use the address to access the class members that both the original address and the copy reference.</span></span> <span data-ttu-id="9b8f8-115">Si el método al que se ha llamado cambia un miembro de clase, la instancia de clase original en el método de llamada también cambia.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-115">If the called method changes a class member, the original class instance in the calling method also changes.</span></span>  
  
 <span data-ttu-id="9b8f8-116">En el resultado del ejemplo siguiente se ilustra la diferencia.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-116">The output of the following example illustrates the difference.</span></span> <span data-ttu-id="9b8f8-117">El valor del campo `willIChange` de la instancia de clase se cambia mediante la llamada al método `ClassTaker` porque el método usa la dirección en el parámetro para buscar el campo especificado de la instancia de clase.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-117">The value of the `willIChange` field of the class instance is changed by the call to method `ClassTaker` because the method uses the address in the parameter to find the specified field of the class instance.</span></span> <span data-ttu-id="9b8f8-118">El campo `willIChange` del struct en el método de llamada no se cambia mediante la llamada al método `StructTaker` porque el valor del argumento es una copia del propio struct, no una copia de su dirección.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-118">The `willIChange` field of the struct in the calling method is not changed by the call to method `StructTaker` because the value of the argument is a copy of the struct itself, not a copy of its address.</span></span> <span data-ttu-id="9b8f8-119">`StructTaker` cambia la copia, y la copia se pierde cuando se completa la llamada a `StructTaker`.</span><span class="sxs-lookup"><span data-stu-id="9b8f8-119">`StructTaker` changes the copy, and the copy is lost when the call to `StructTaker` is completed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b8f8-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9b8f8-120">Example</span></span>  
 <span data-ttu-id="9b8f8-121">[!code-cs[csProgGuideObjects#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9b8f8-121">[!code-cs[csProgGuideObjects#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b8f8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b8f8-122">See Also</span></span>  
 <span data-ttu-id="9b8f8-123">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9b8f8-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9b8f8-124">[Clases](../../../csharp/programming-guide/classes-and-structs/classes.md) </span><span class="sxs-lookup"><span data-stu-id="9b8f8-124">[Classes](../../../csharp/programming-guide/classes-and-structs/classes.md) </span></span>  
 <span data-ttu-id="9b8f8-125">[Structs](../../../csharp/programming-guide/classes-and-structs/structs.md) </span><span class="sxs-lookup"><span data-stu-id="9b8f8-125">[Structs](../../../csharp/programming-guide/classes-and-structs/structs.md) </span></span>  
 [<span data-ttu-id="9b8f8-126">Pasar parámetros</span><span class="sxs-lookup"><span data-stu-id="9b8f8-126">Passing Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)

