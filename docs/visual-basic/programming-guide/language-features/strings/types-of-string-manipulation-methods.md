---
title: "Tipos de métodos de manipulación de cadenas en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b437be4a6f4a0cc9d5a4d21291a80c9cb8fffcd3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="1b0c2-102">Tipos de métodos de manipulación de cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1b0c2-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="1b0c2-103">Hay varias maneras de analizar y manipular las cadenas.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="1b0c2-104">Algunos de los métodos forman parte de la [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] idioma, mientras que otras son inherentes a la `String` clase.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-104">Some of the methods are a part of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="1b0c2-105">Lenguaje Visual Basic y .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1b0c2-105">Visual Basic Language and the .NET Framework</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="1b0c2-106">métodos se utilizan como funciones inherentes del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-106"> methods are used as inherent functions of the language.</span></span> <span data-ttu-id="1b0c2-107">Se puede utilizar sin calificación en el código.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="1b0c2-108">En el ejemplo siguiente se muestra el uso típico de un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] comando de manipulación de cadenas:</span><span class="sxs-lookup"><span data-stu-id="1b0c2-108">The following example shows typical use of a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 <span data-ttu-id="1b0c2-109">En este ejemplo, el `Mid` función realiza una operación directa en `aString` y asigna el valor a `bString`.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="1b0c2-110">Para obtener una lista de métodos de manipulación de cadenas de Visual Basic, consulte [resumen de manipulación de cadenas](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="1b0c2-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="1b0c2-111">Métodos compartidos y métodos de instancia</span><span class="sxs-lookup"><span data-stu-id="1b0c2-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="1b0c2-112">También puede manipular cadenas con los métodos de la `String` clase.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="1b0c2-113">Hay dos tipos de métodos de `String`: *compartido* métodos y *instancia* métodos.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="1b0c2-114">Métodos compartidos</span><span class="sxs-lookup"><span data-stu-id="1b0c2-114">Shared Methods</span></span>  
 <span data-ttu-id="1b0c2-115">Un método compartido es un método que proviene de la `String` propia clase y no requiere una instancia de dicha clase para funcionar.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="1b0c2-116">Estos métodos se pueden calificar con el nombre de la clase (`String`) en lugar de con una instancia de la `String` clase.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="1b0c2-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1b0c2-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 <span data-ttu-id="1b0c2-118">En el ejemplo anterior, el <xref:System.String.Copy%2A?displayProperty=nameWithType> método es un método estático, que actúa sobre una expresión dada y asigna el valor resultante al `bString`.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="1b0c2-119">Métodos de instancia</span><span class="sxs-lookup"><span data-stu-id="1b0c2-119">Instance Methods</span></span>  
 <span data-ttu-id="1b0c2-120">Métodos de instancia, por el contrario, se derivan de una instancia determinada de `String` y deben estar calificados con el nombre de instancia.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="1b0c2-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1b0c2-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 <span data-ttu-id="1b0c2-122">En este ejemplo, el <xref:System.String.Substring%2A?displayProperty=nameWithType> método es un método de la instancia de `String` (es decir, `aString`).</span><span class="sxs-lookup"><span data-stu-id="1b0c2-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="1b0c2-123">Realiza una operación en `aString` y asigna ese valor a `bString`.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="1b0c2-124">Para obtener más información, consulte la documentación para el <xref:System.String> clase.</span><span class="sxs-lookup"><span data-stu-id="1b0c2-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b0c2-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b0c2-125">See Also</span></span>  
 [<span data-ttu-id="1b0c2-126">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1b0c2-126">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
