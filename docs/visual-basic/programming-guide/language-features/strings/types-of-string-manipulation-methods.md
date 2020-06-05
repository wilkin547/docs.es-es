---
title: Tipos de métodos de manipulación de cadenas
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: aba9af9c699cf8d07862c5d2967902bec1623500
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363764"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="8c03e-102">Tipos de métodos de manipulación de cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c03e-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="8c03e-103">Hay varias maneras de analizar y manipular las cadenas.</span><span class="sxs-lookup"><span data-stu-id="8c03e-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="8c03e-104">Algunos de los métodos forman parte del lenguaje Visual Basic y otros son inherentes a la `String` clase.</span><span class="sxs-lookup"><span data-stu-id="8c03e-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="8c03e-105">Visual Basic idioma y el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8c03e-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="8c03e-106">Visual Basic métodos se usan como funciones inherentes del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="8c03e-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="8c03e-107">Se pueden usar sin calificación en el código.</span><span class="sxs-lookup"><span data-stu-id="8c03e-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="8c03e-108">En el ejemplo siguiente se muestra el uso típico de un comando de manipulación de cadenas Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="8c03e-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 <span data-ttu-id="8c03e-109">En este ejemplo, la `Mid` función realiza una operación directa en `aString` y asigna el valor a `bString` .</span><span class="sxs-lookup"><span data-stu-id="8c03e-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="8c03e-110">Para obtener una lista de los métodos de manipulación de cadenas de Visual Basic, vea Resumen de la [manipulación de cadenas](../../../language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="8c03e-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="8c03e-111">Métodos compartidos y métodos de instancia</span><span class="sxs-lookup"><span data-stu-id="8c03e-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="8c03e-112">También puede manipular cadenas con los métodos de la `String` clase.</span><span class="sxs-lookup"><span data-stu-id="8c03e-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="8c03e-113">Hay dos tipos de métodos en `String` : métodos *compartidos* y métodos de *instancia* .</span><span class="sxs-lookup"><span data-stu-id="8c03e-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="8c03e-114">Métodos compartidos</span><span class="sxs-lookup"><span data-stu-id="8c03e-114">Shared Methods</span></span>  
 <span data-ttu-id="8c03e-115">Un método compartido es un método que se deriva de la `String` propia clase y no requiere que una instancia de esa clase funcione.</span><span class="sxs-lookup"><span data-stu-id="8c03e-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="8c03e-116">Estos métodos se pueden calificar con el nombre de la clase ( `String` ) en lugar de con una instancia de la `String` clase.</span><span class="sxs-lookup"><span data-stu-id="8c03e-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="8c03e-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8c03e-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 <span data-ttu-id="8c03e-118">En el ejemplo anterior, el <xref:System.String.Copy%2A?displayProperty=nameWithType> método es un método estático, que actúa sobre una expresión que se proporciona y asigna el valor resultante a `bString` .</span><span class="sxs-lookup"><span data-stu-id="8c03e-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="8c03e-119">Métodos de instancia</span><span class="sxs-lookup"><span data-stu-id="8c03e-119">Instance Methods</span></span>  
 <span data-ttu-id="8c03e-120">Por el contrario, los métodos de instancia proceden de una instancia determinada de `String` y se deben calificar con el nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="8c03e-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="8c03e-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8c03e-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 <span data-ttu-id="8c03e-122">En este ejemplo, el <xref:System.String.Substring%2A?displayProperty=nameWithType> método es un método de la instancia de `String` (es decir, `aString` ).</span><span class="sxs-lookup"><span data-stu-id="8c03e-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="8c03e-123">Realiza una operación en `aString` y asigna ese valor a `bString` .</span><span class="sxs-lookup"><span data-stu-id="8c03e-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="8c03e-124">Para obtener más información, vea la documentación de la <xref:System.String> clase.</span><span class="sxs-lookup"><span data-stu-id="8c03e-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c03e-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c03e-125">See also</span></span>

- [<span data-ttu-id="8c03e-126">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c03e-126">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
