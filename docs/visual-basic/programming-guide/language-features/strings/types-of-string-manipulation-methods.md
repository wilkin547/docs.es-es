---
title: Tipos de métodos de manipulación de cadenas en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: a75984d0eb64ef8c18def3ae59d5e1f4b6d20ce2
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980352"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="cf579-102">Tipos de métodos de manipulación de cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf579-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="cf579-103">Hay varias maneras de analizar y manipular las cadenas.</span><span class="sxs-lookup"><span data-stu-id="cf579-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="cf579-104">Algunos de los métodos son una parte del lenguaje Visual Basic y otros son inherentes a la `String` clase.</span><span class="sxs-lookup"><span data-stu-id="cf579-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="cf579-105">Lenguaje Visual Basic y .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cf579-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="cf579-106">Métodos de Visual Basic se usan como funciones inherentes del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="cf579-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="cf579-107">Se puede usar sin calificación en el código.</span><span class="sxs-lookup"><span data-stu-id="cf579-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="cf579-108">El ejemplo siguiente muestra un uso típico de un comando de manipulación de cadenas de Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="cf579-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 <span data-ttu-id="cf579-109">En este ejemplo, el `Mid` función realiza una operación directa en `aString` y asigna el valor a `bString`.</span><span class="sxs-lookup"><span data-stu-id="cf579-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="cf579-110">Para obtener una lista de métodos de manipulación de cadenas de Visual Basic, vea [resumen de manipulación de cadenas](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="cf579-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="cf579-111">Métodos compartidos y métodos de instancia</span><span class="sxs-lookup"><span data-stu-id="cf579-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="cf579-112">También puede manipular cadenas con los métodos de la `String` clase.</span><span class="sxs-lookup"><span data-stu-id="cf579-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="cf579-113">Hay dos tipos de métodos de `String`: *compartido* métodos y *instancia* métodos.</span><span class="sxs-lookup"><span data-stu-id="cf579-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="cf579-114">Métodos compartidos</span><span class="sxs-lookup"><span data-stu-id="cf579-114">Shared Methods</span></span>  
 <span data-ttu-id="cf579-115">Un método compartido es un método que se deriva el `String` propia clase y no requiere una instancia de esa clase para que funcionen.</span><span class="sxs-lookup"><span data-stu-id="cf579-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="cf579-116">Estos métodos se pueden calificar con el nombre de la clase (`String`) en lugar de con una instancia de la `String` clase.</span><span class="sxs-lookup"><span data-stu-id="cf579-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="cf579-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf579-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 <span data-ttu-id="cf579-118">En el ejemplo anterior, el <xref:System.String.Copy%2A?displayProperty=nameWithType> método es un método estático, que actúa sobre una expresión dada y asigna el valor resultante a `bString`.</span><span class="sxs-lookup"><span data-stu-id="cf579-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="cf579-119">Métodos de instancia</span><span class="sxs-lookup"><span data-stu-id="cf579-119">Instance Methods</span></span>  
 <span data-ttu-id="cf579-120">Métodos de instancia, por el contrario, se derivan de una instancia determinada de `String` y deben estar calificados con el nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="cf579-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="cf579-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cf579-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 <span data-ttu-id="cf579-122">En este ejemplo, el <xref:System.String.Substring%2A?displayProperty=nameWithType> método es un método de la instancia de `String` (es decir, `aString`).</span><span class="sxs-lookup"><span data-stu-id="cf579-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="cf579-123">Realiza una operación en `aString` y asigna ese valor a `bString`.</span><span class="sxs-lookup"><span data-stu-id="cf579-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="cf579-124">Para obtener más información, consulte la documentación para el <xref:System.String> clase.</span><span class="sxs-lookup"><span data-stu-id="cf579-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf579-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf579-125">See also</span></span>
- [<span data-ttu-id="cf579-126">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf579-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
