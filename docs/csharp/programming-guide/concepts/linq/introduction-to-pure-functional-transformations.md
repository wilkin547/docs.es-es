---
title: "Introducción a las transformaciones funcionales puras (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 8495c9d9-2d02-4aa0-8a10-9e8794b985fe
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 34c4b94577291f300dd2a14ffc33a5ec04b31782
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="introduction-to-pure-functional-transformations-c"></a><span data-ttu-id="ccfdc-102">Introducción a las transformaciones funcionales puras (C#)</span><span class="sxs-lookup"><span data-stu-id="ccfdc-102">Introduction to Pure Functional Transformations (C#)</span></span>
<span data-ttu-id="ccfdc-103">Esta sección ofrece una introducción a las transformaciones funcionales, incluyendo los conceptos subyacentes y los constructores del lenguaje que las hacen posible.</span><span class="sxs-lookup"><span data-stu-id="ccfdc-103">This section introduces functional transformations, including the underlying concepts and supporting language constructs.</span></span> <span data-ttu-id="ccfdc-104">Realiza una comparación entre las metodologías de programación de orientación a objetos y de transformación funcional, incluyendo consejos acerca de cómo llevar a cabo la transición a ésta última.</span><span class="sxs-lookup"><span data-stu-id="ccfdc-104">It contrasts the object-oriented and functional transformation approaches to programming, including advice on how to transition to the latter.</span></span> <span data-ttu-id="ccfdc-105">Aunque es posible utiliza las transformaciones funcionales en numerosos escenarios, aquí utilizaremos la transformación XML como un ejemplo concreto.</span><span class="sxs-lookup"><span data-stu-id="ccfdc-105">Although functional transformations can be used in many programming scenarios, XML transformation is used here as a concrete example.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ccfdc-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ccfdc-106">In This Section</span></span>  
  
|<span data-ttu-id="ccfdc-107">Tema</span><span class="sxs-lookup"><span data-stu-id="ccfdc-107">Topic</span></span>|<span data-ttu-id="ccfdc-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ccfdc-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="ccfdc-109">Conceptos y terminología (transformación funcional) (C#)</span><span class="sxs-lookup"><span data-stu-id="ccfdc-109">Concepts and Terminology (Functional Transformation) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)|<span data-ttu-id="ccfdc-110">Presenta los conceptos y la terminología en relación con las transformaciones funcionales.</span><span class="sxs-lookup"><span data-stu-id="ccfdc-110">Introduces the concepts and terminology of pure functional transformations.</span></span>|  
|[<span data-ttu-id="ccfdc-111">Diferencias entre la programación funcional y programación imperativa (C#)</span><span class="sxs-lookup"><span data-stu-id="ccfdc-111">Functional Programming vs. Imperative Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)|<span data-ttu-id="ccfdc-112">Compara y contrasta la programación funcional con la programación imperativa (orientada a procedimientos) más tradicional.</span><span class="sxs-lookup"><span data-stu-id="ccfdc-112">Compares and contrasts functional programming to more traditional imperative (procedural) programming.</span></span>|  
|[<span data-ttu-id="ccfdc-113">Refactorizar en funciones puras (C#)</span><span class="sxs-lookup"><span data-stu-id="ccfdc-113">Refactoring Into Pure Functions (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md)|<span data-ttu-id="ccfdc-114">Presenta las funciones puras y muestra ejemplos de funciones puras e impuras.</span><span class="sxs-lookup"><span data-stu-id="ccfdc-114">Introduces pure functions, and shows examples of and pure and impure functions.</span></span>|  
|[<span data-ttu-id="ccfdc-115">Aplicabilidad de la transformación funcional (C#)</span><span class="sxs-lookup"><span data-stu-id="ccfdc-115">Applicability of Functional Transformation (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/applicability-of-functional-transformation.md)|<span data-ttu-id="ccfdc-116">Describe los escenarios típicos donde se realizan transformaciones funcionales.</span><span class="sxs-lookup"><span data-stu-id="ccfdc-116">Describes typical scenarios for functional transformations.</span></span>|  
|[<span data-ttu-id="ccfdc-117">Transformación funcional de XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ccfdc-117">Functional Transformation of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md)|<span data-ttu-id="ccfdc-118">Describe las transformaciones funcionales en el contexto de los árboles XML de transformación.</span><span class="sxs-lookup"><span data-stu-id="ccfdc-118">Describes functional transformations in the context of transforming XML trees.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ccfdc-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccfdc-119">See Also</span></span>  
 [<span data-ttu-id="ccfdc-120">Transformaciones funcionales puras de XML (C#)</span><span class="sxs-lookup"><span data-stu-id="ccfdc-120">Pure Functional Transformations of XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)

