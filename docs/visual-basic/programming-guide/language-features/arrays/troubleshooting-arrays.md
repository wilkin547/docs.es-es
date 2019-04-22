---
title: Solucionar problemas de matrices (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 2b051d22fe3d331626f2e181c008043e576b7526
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833378"
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="2281a-102">Solucionar problemas de matrices (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2281a-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="2281a-103">Esta página enumera algunos problemas comunes que pueden producirse al trabajar con matrices.</span><span class="sxs-lookup"><span data-stu-id="2281a-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="2281a-104">Errores de compilación declarar e inicializar una matriz</span><span class="sxs-lookup"><span data-stu-id="2281a-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="2281a-105">Pueden surgir errores de compilación de falta de comprensión de las reglas para declarar, crear e inicializar matrices.</span><span class="sxs-lookup"><span data-stu-id="2281a-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="2281a-106">Las causas más comunes de errores son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="2281a-106">The most common causes of errors are the following:</span></span>  
  
-   <span data-ttu-id="2281a-107">Proporcionar un [nuevo operador](../../../../visual-basic/language-reference/operators/new-operator.md) cláusula después de especificar longitudes de dimensión en la declaración de variable de matriz.</span><span class="sxs-lookup"><span data-stu-id="2281a-107">Supplying a [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="2281a-108">Las líneas de código siguiente muestran declaraciones no válidas de este tipo.</span><span class="sxs-lookup"><span data-stu-id="2281a-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   <span data-ttu-id="2281a-109">Especificar longitudes de dimensión durante más de la matriz de nivel superior de una matriz escalonada.</span><span class="sxs-lookup"><span data-stu-id="2281a-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="2281a-110">La línea de código siguiente muestra una declaración no válida de este tipo.</span><span class="sxs-lookup"><span data-stu-id="2281a-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   <span data-ttu-id="2281a-111">Si se omite el `New` palabra clave al especificar los valores de elemento.</span><span class="sxs-lookup"><span data-stu-id="2281a-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="2281a-112">La línea de código siguiente muestra una declaración no válida de este tipo.</span><span class="sxs-lookup"><span data-stu-id="2281a-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   <span data-ttu-id="2281a-113">Proporcionar un `New` cláusula sin llaves (`{}`).</span><span class="sxs-lookup"><span data-stu-id="2281a-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="2281a-114">Las líneas de código siguiente muestran declaraciones no válidas de este tipo.</span><span class="sxs-lookup"><span data-stu-id="2281a-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="2281a-115">Obtener acceso a una matriz fuera de los límites</span><span class="sxs-lookup"><span data-stu-id="2281a-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="2281a-116">El proceso de inicialización de una matriz asigna un límite superior y un límite inferior para cada dimensión.</span><span class="sxs-lookup"><span data-stu-id="2281a-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="2281a-117">Cada acceso a un elemento de la matriz debe especificar un índice válido, o subíndice, para cada dimensión.</span><span class="sxs-lookup"><span data-stu-id="2281a-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="2281a-118">Si un índice está por debajo de su límite inferior o por encima de su límite superior, un <xref:System.IndexOutOfRangeException> resultados de la excepción.</span><span class="sxs-lookup"><span data-stu-id="2281a-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="2281a-119">El compilador no puede detectar este tipo de error, por lo que se produce un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2281a-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="2281a-120">Determinar los límites</span><span class="sxs-lookup"><span data-stu-id="2281a-120">Determining Bounds</span></span>  
 <span data-ttu-id="2281a-121">Si otro componente pasa una matriz en el código, por ejemplo como un argumento de procedimiento, no conoce el tamaño de la matriz o las longitudes de sus dimensiones.</span><span class="sxs-lookup"><span data-stu-id="2281a-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="2281a-122">Siempre debe determinar el límite superior para cada dimensión de la matriz antes de intentar tener acceso a todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="2281a-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="2281a-123">Si se ha creado la matriz por otros medios distintos de Visual Basic `New` cláusula, el límite inferior podría ser algo distinto de 0, y es más seguro determinar también ese límite inferior.</span><span class="sxs-lookup"><span data-stu-id="2281a-123">If the array has been created by some means other than a Visual Basic `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="2281a-124">Especifica la dimensión</span><span class="sxs-lookup"><span data-stu-id="2281a-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="2281a-125">Al determinar los límites de una matriz multidimensional, tenga cuidado de cómo especificar la dimensión.</span><span class="sxs-lookup"><span data-stu-id="2281a-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="2281a-126">El `dimension` parámetros de la <xref:System.Array.GetLowerBound%2A> y <xref:System.Array.GetUpperBound%2A> métodos están basados en 0, mientras el `Rank` parámetros de Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> y <xref:Microsoft.VisualBasic.Information.UBound%2A> funciones están basadas en 1.</span><span class="sxs-lookup"><span data-stu-id="2281a-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2281a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="2281a-127">See also</span></span>

- [<span data-ttu-id="2281a-128">Matrices</span><span class="sxs-lookup"><span data-stu-id="2281a-128">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="2281a-129">Cómo: Inicializar una Variable de matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2281a-129">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
