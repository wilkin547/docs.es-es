---
title: Limitaciones de Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 97a2e162b9f1a673fbe805a5d2ef1421cd423a4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="d1d91-102">Limitaciones de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1d91-102">Visual Basic Limitations</span></span>
<span data-ttu-id="d1d91-103">Las versiones anteriores de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] aplica límites en el código, como la longitud de los nombres de variable, el número de variables permitidas en los módulos y tamaño de los módulos.</span><span class="sxs-lookup"><span data-stu-id="d1d91-103">Earlier versions of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="d1d91-104">En Visual Basic. NET, se han reducido estas restricciones, lo que le proporciona mayor libertad para crear y organizar el código.</span><span class="sxs-lookup"><span data-stu-id="d1d91-104">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="d1d91-105">Límites físicos dependen más de memoria en tiempo de ejecución que en las consideraciones de tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d1d91-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="d1d91-106">Si se utilizan prácticas de programación prudentes y aplicaciones grandes se dividen en varias clases y módulos, hay muy pocas probabilidades de encontrar un interno [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] limitación.</span><span class="sxs-lookup"><span data-stu-id="d1d91-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] limitation.</span></span>  
  
 <span data-ttu-id="d1d91-107">Las siguientes son algunas limitaciones que pueden surgir en casos extremos:</span><span class="sxs-lookup"><span data-stu-id="d1d91-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
-   <span data-ttu-id="d1d91-108">**Longitud del nombre.**</span><span class="sxs-lookup"><span data-stu-id="d1d91-108">**Name Length.**</span></span> <span data-ttu-id="d1d91-109">Hay un número máximo de caracteres para el nombre de cada elemento de programación declarado.</span><span class="sxs-lookup"><span data-stu-id="d1d91-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="d1d91-110">Este valor máximo se aplica a una cadena de calificación completa si hay que califica el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="d1d91-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="d1d91-111">Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="d1d91-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   <span data-ttu-id="d1d91-112">**Longitud de línea.**</span><span class="sxs-lookup"><span data-stu-id="d1d91-112">**Line Length.**</span></span> <span data-ttu-id="d1d91-113">Hay un máximo de 65535 caracteres en una línea física de código fuente.</span><span class="sxs-lookup"><span data-stu-id="d1d91-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="d1d91-114">La línea de código de origen lógico puede tener más si se usan caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="d1d91-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="d1d91-115">Vea [Cómo: interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="d1d91-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
-   <span data-ttu-id="d1d91-116">**Dimensiones de la matriz.**</span><span class="sxs-lookup"><span data-stu-id="d1d91-116">**Array Dimensions.**</span></span> <span data-ttu-id="d1d91-117">Hay un número máximo de dimensiones que se pueden declarar para una matriz.</span><span class="sxs-lookup"><span data-stu-id="d1d91-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="d1d91-118">Esto limita cuántos índices se pueden utilizar para especificar un elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="d1d91-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="d1d91-119">Vea [matriz dimensiones en Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="d1d91-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
-   <span data-ttu-id="d1d91-120">**Longitud de cadena.**</span><span class="sxs-lookup"><span data-stu-id="d1d91-120">**String Length.**</span></span> <span data-ttu-id="d1d91-121">Hay un número máximo de caracteres Unicode que pueden almacenar en una sola cadena.</span><span class="sxs-lookup"><span data-stu-id="d1d91-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="d1d91-122">Vea [tipo de datos de cadena](../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="d1d91-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
-   <span data-ttu-id="d1d91-123">**Longitud de la cadena de entorno.**</span><span class="sxs-lookup"><span data-stu-id="d1d91-123">**Environment String Length.**</span></span> <span data-ttu-id="d1d91-124">Hay un máximo de 32768 caracteres para cualquier cadena de entorno que se usa como un argumento de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d1d91-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="d1d91-125">Se trata de una limitación en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="d1d91-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1d91-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1d91-126">See Also</span></span>  
 [<span data-ttu-id="d1d91-127">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="d1d91-127">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="d1d91-128">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1d91-128">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
