---
title: Procedimiento para crear un método nuevo para una enumeración - Guía de programación de C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 02af55c851392ce5dde4c83fd32d18b927950a3f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971030"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="9ba05-102">Procedimiento para crear un método nuevo para una enumeración (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9ba05-102">How to create a new method for an enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="9ba05-103">Puede usar métodos de extensión para agregar funcionalidad a un tipo de enumeración concreto.</span><span class="sxs-lookup"><span data-stu-id="9ba05-103">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ba05-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ba05-104">Example</span></span>  
 <span data-ttu-id="9ba05-105">En el ejemplo siguiente, la enumeración `Grades` representa las posibles calificaciones con letras que un alumno puede recibir en una clase.</span><span class="sxs-lookup"><span data-stu-id="9ba05-105">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="9ba05-106">Un método de extensión denominado `Passing` se agrega al tipo `Grades` para que cada instancia de ese tipo "sepa" ahora si representa una calificación de aprobado o no.</span><span class="sxs-lookup"><span data-stu-id="9ba05-106">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 <span data-ttu-id="9ba05-107">Tenga en cuenta que la clase `Extensions` también contiene una variable estática que se actualiza dinámicamente y que el valor devuelto del método de extensión refleja el valor actual de esa variable.</span><span class="sxs-lookup"><span data-stu-id="9ba05-107">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="9ba05-108">Esto demuestra que, en segundo plano, los métodos de extensión se invocan directamente en la clase estática en donde se definen.</span><span class="sxs-lookup"><span data-stu-id="9ba05-108">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ba05-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ba05-109">See also</span></span>

- [<span data-ttu-id="9ba05-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9ba05-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9ba05-111">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="9ba05-111">Extension Methods</span></span>](./extension-methods.md)
