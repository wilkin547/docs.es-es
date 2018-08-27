---
title: Tipo parcial (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 362a02815cb249d57c0bd19706714df1d71644f4
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929668"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="4a9ea-102">Tipo parcial (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4a9ea-102">partial (Type) (C# Reference)</span></span>
<span data-ttu-id="4a9ea-103">Las definiciones de tipo parcial permiten dividir la definición de una clase, estructura o interfaz en varios archivos.</span><span class="sxs-lookup"><span data-stu-id="4a9ea-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>  
  
 <span data-ttu-id="4a9ea-104">En File1.cs:</span><span class="sxs-lookup"><span data-stu-id="4a9ea-104">In File1.cs:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_1.cs)]  
  
 <span data-ttu-id="4a9ea-105">La declaración en File2.cs:</span><span class="sxs-lookup"><span data-stu-id="4a9ea-105">In File2.cs the declaration:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="4a9ea-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4a9ea-106">Remarks</span></span>  
 <span data-ttu-id="4a9ea-107">Dividir un tipo de clase, estructura o interfaz en varios archivos puede resultar útil cuando trabaja con proyectos de gran tamaño o con código generado automáticamente, como el proporcionado por el [Diseñador de Windows Forms](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="4a9ea-107">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="4a9ea-108">Un tipo parcial puede contener un [método parcial](../../../csharp/language-reference/keywords/partial-method.md).</span><span class="sxs-lookup"><span data-stu-id="4a9ea-108">A partial type may contain a [partial method](../../../csharp/language-reference/keywords/partial-method.md).</span></span> <span data-ttu-id="4a9ea-109">Para obtener más información, consulte [Clases y métodos parciales](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="4a9ea-109">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4a9ea-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4a9ea-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4a9ea-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a9ea-111">See Also</span></span>

- [<span data-ttu-id="4a9ea-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="4a9ea-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="4a9ea-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4a9ea-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="4a9ea-114">Modificadores</span><span class="sxs-lookup"><span data-stu-id="4a9ea-114">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
- [<span data-ttu-id="4a9ea-115">Introducción a los genéricos</span><span class="sxs-lookup"><span data-stu-id="4a9ea-115">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)
