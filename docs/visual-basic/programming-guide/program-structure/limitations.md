---
description: 'Más información acerca de: limitaciones de Visual Basic'
title: Limitaciones
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: 9182c5fe475e4350cb17ed3e4b734e3924bb9f7b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432850"
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="37df0-103">Limitaciones de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37df0-103">Visual Basic Limitations</span></span>

<span data-ttu-id="37df0-104">Las versiones anteriores de Visual Basic los límites aplicados en el código, como la longitud de los nombres de variable, el número de variables permitidas en los módulos y el tamaño del módulo.</span><span class="sxs-lookup"><span data-stu-id="37df0-104">Earlier versions of Visual Basic enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="37df0-105">En Visual Basic .NET, estas restricciones se han reducido, lo que le aporta mayor libertad para escribir y organizar el código.</span><span class="sxs-lookup"><span data-stu-id="37df0-105">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="37df0-106">Los límites físicos dependen más en la memoria en tiempo de ejecución que en las consideraciones en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="37df0-106">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="37df0-107">Si usa prácticas de programación prudentes y divide aplicaciones grandes en varias clases y módulos, hay muy pocas probabilidades de encontrar una limitación de Visual Basic interna.</span><span class="sxs-lookup"><span data-stu-id="37df0-107">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal Visual Basic limitation.</span></span>  
  
 <span data-ttu-id="37df0-108">A continuación se indican algunas limitaciones que pueden surgir en casos extremos:</span><span class="sxs-lookup"><span data-stu-id="37df0-108">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
- <span data-ttu-id="37df0-109">**Longitud del nombre.**</span><span class="sxs-lookup"><span data-stu-id="37df0-109">**Name Length.**</span></span> <span data-ttu-id="37df0-110">Hay un número máximo de caracteres para el nombre de cada elemento de programación declarado.</span><span class="sxs-lookup"><span data-stu-id="37df0-110">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="37df0-111">Este máximo se aplica a toda la cadena de calificación si el nombre del elemento está calificado.</span><span class="sxs-lookup"><span data-stu-id="37df0-111">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="37df0-112">Vea [Declared Element Names](../language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="37df0-112">See [Declared Element Names](../language-features/declared-elements/declared-element-names.md).</span></span>  
  
- <span data-ttu-id="37df0-113">**Longitud de línea.**</span><span class="sxs-lookup"><span data-stu-id="37df0-113">**Line Length.**</span></span> <span data-ttu-id="37df0-114">Hay un máximo de 65535 caracteres en una línea física de código fuente.</span><span class="sxs-lookup"><span data-stu-id="37df0-114">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="37df0-115">La línea de código fuente lógica puede ser más larga si usa caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="37df0-115">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="37df0-116">Vea [Cómo: interrumpir y combinar instrucciones en el código](how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="37df0-116">See [How to: Break and Combine Statements in Code](how-to-break-and-combine-statements-in-code.md).</span></span>  
  
- <span data-ttu-id="37df0-117">**Dimensiones de la matriz.**</span><span class="sxs-lookup"><span data-stu-id="37df0-117">**Array Dimensions.**</span></span> <span data-ttu-id="37df0-118">Hay un número máximo de dimensiones que puede declarar para una matriz.</span><span class="sxs-lookup"><span data-stu-id="37df0-118">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="37df0-119">Esto limita el número de índices que puede utilizar para especificar un elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="37df0-119">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="37df0-120">Vea [dimensiones de la matriz en Visual Basic](../language-features/arrays/array-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="37df0-120">See [Array Dimensions in Visual Basic](../language-features/arrays/array-dimensions.md).</span></span>  
  
- <span data-ttu-id="37df0-121">**Longitud de la cadena.**</span><span class="sxs-lookup"><span data-stu-id="37df0-121">**String Length.**</span></span> <span data-ttu-id="37df0-122">Hay un número máximo de caracteres Unicode que se pueden almacenar en una sola cadena.</span><span class="sxs-lookup"><span data-stu-id="37df0-122">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="37df0-123">Vea [tipo de datos de cadena](../../language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="37df0-123">See [String Data Type](../../language-reference/data-types/string-data-type.md).</span></span>  
  
- <span data-ttu-id="37df0-124">**Longitud de la cadena de entorno.**</span><span class="sxs-lookup"><span data-stu-id="37df0-124">**Environment String Length.**</span></span> <span data-ttu-id="37df0-125">Hay un máximo de 32768 caracteres para cualquier cadena de entorno utilizada como argumento de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="37df0-125">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="37df0-126">Se trata de una limitación en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="37df0-126">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37df0-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37df0-127">See also</span></span>

- [<span data-ttu-id="37df0-128">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="37df0-128">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="37df0-129">Convenciones de nomenclatura de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37df0-129">Visual Basic Naming Conventions</span></span>](naming-conventions.md)
