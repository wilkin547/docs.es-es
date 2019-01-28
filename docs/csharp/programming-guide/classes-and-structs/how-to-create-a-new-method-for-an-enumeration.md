---
title: 'Procedimiento Crear un método nuevo para una enumeración: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 411606b6d86f8781be0cb2db19474d563c09a610
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725134"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="489d3-102">Procedimiento Crear un método nuevo para una enumeración (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="489d3-102">How to: Create a New Method for an Enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="489d3-103">Puede usar métodos de extensión para agregar funcionalidad a un tipo de enumeración concreto.</span><span class="sxs-lookup"><span data-stu-id="489d3-103">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="489d3-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="489d3-104">Example</span></span>  
 <span data-ttu-id="489d3-105">En el ejemplo siguiente, la enumeración `Grades` representa las posibles calificaciones con letras que un alumno puede recibir en una clase.</span><span class="sxs-lookup"><span data-stu-id="489d3-105">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="489d3-106">Un método de extensión denominado `Passing` se agrega al tipo `Grades` para que cada instancia de ese tipo "sepa" ahora si representa una calificación de aprobado o no.</span><span class="sxs-lookup"><span data-stu-id="489d3-106">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-create-a-new-method-for-an-enumeration_1.cs)]  
  
 <span data-ttu-id="489d3-107">Tenga en cuenta que la clase `Extensions` también contiene una variable estática que se actualiza dinámicamente y que el valor devuelto del método de extensión refleja el valor actual de esa variable.</span><span class="sxs-lookup"><span data-stu-id="489d3-107">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="489d3-108">Esto demuestra que, en segundo plano, los métodos de extensión se invocan directamente en la clase estática en donde se definen.</span><span class="sxs-lookup"><span data-stu-id="489d3-108">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="489d3-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="489d3-109">Compiling the Code</span></span>  
 <span data-ttu-id="489d3-110">Para ejecutar este código, cópielo y péguelo en un proyecto de aplicación de consola de Visual C# creado en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="489d3-110">To run this code, copy and paste it into a Visual C# console application project that has been created in Visual Studio.</span></span> <span data-ttu-id="489d3-111">De forma predeterminada, este proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] y tiene una referencia a System.Core.dll y una directiva `using` para System.Linq.</span><span class="sxs-lookup"><span data-stu-id="489d3-111">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="489d3-112">Si faltan alguno de estos requisitos del proyecto, se puede agregar manualmente.</span><span class="sxs-lookup"><span data-stu-id="489d3-112">If one or more of these requirements are missing from the project, you can add them manually.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="489d3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="489d3-113">See also</span></span>

- [<span data-ttu-id="489d3-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="489d3-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="489d3-115">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="489d3-115">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
