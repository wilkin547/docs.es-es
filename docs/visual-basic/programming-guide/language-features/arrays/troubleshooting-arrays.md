---
title: Solución de problemas de matrices
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: e633c5a00693f188270b1610abaf2decb656b00a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414600"
---
# <a name="troubleshooting-arrays-visual-basic"></a><span data-ttu-id="4b25f-102">Solucionar problemas de matrices (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b25f-102">Troubleshooting Arrays (Visual Basic)</span></span>
<span data-ttu-id="4b25f-103">En esta página se enumeran algunos problemas comunes que pueden producirse al trabajar con matrices.</span><span class="sxs-lookup"><span data-stu-id="4b25f-103">This page lists some common problems that can occur when working with arrays.</span></span>  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a><span data-ttu-id="4b25f-104">Errores de compilación que declaran e inicializan una matriz</span><span class="sxs-lookup"><span data-stu-id="4b25f-104">Compilation Errors Declaring and Initializing an Array</span></span>  
 <span data-ttu-id="4b25f-105">Pueden surgir errores de compilación debido a la incomprensión de las reglas para declarar, crear e inicializar matrices.</span><span class="sxs-lookup"><span data-stu-id="4b25f-105">Compilation errors can arise from misunderstanding of the rules for declaring, creating, and initializing arrays.</span></span> <span data-ttu-id="4b25f-106">Las causas más comunes de los errores son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="4b25f-106">The most common causes of errors are the following:</span></span>  
  
- <span data-ttu-id="4b25f-107">Proporcionar una [nueva cláusula Operator](../../../language-reference/operators/new-operator.md) después de especificar la longitud de la dimensión en la declaración de la variable de matriz.</span><span class="sxs-lookup"><span data-stu-id="4b25f-107">Supplying a [New Operator](../../../language-reference/operators/new-operator.md) clause after specifying dimension lengths in the array variable declaration.</span></span> <span data-ttu-id="4b25f-108">En las líneas de código siguientes se muestran declaraciones no válidas de este tipo.</span><span class="sxs-lookup"><span data-stu-id="4b25f-108">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- <span data-ttu-id="4b25f-109">Especificar longitudes de dimensión para más que la matriz de nivel superior de una matriz escalonada.</span><span class="sxs-lookup"><span data-stu-id="4b25f-109">Specifying dimension lengths for more than the top-level array of a jagged array.</span></span> <span data-ttu-id="4b25f-110">En la línea de código siguiente se muestra una declaración no válida de este tipo.</span><span class="sxs-lookup"><span data-stu-id="4b25f-110">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- <span data-ttu-id="4b25f-111">Omitiendo la `New` palabra clave al especificar los valores de elemento.</span><span class="sxs-lookup"><span data-stu-id="4b25f-111">Omitting the `New` keyword when specifying the element values.</span></span> <span data-ttu-id="4b25f-112">En la línea de código siguiente se muestra una declaración no válida de este tipo.</span><span class="sxs-lookup"><span data-stu-id="4b25f-112">The following code line shows an invalid declaration of this type.</span></span>  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- <span data-ttu-id="4b25f-113">Proporcionar una `New` cláusula sin llaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="4b25f-113">Supplying a `New` clause without braces (`{}`).</span></span> <span data-ttu-id="4b25f-114">En las líneas de código siguientes se muestran declaraciones no válidas de este tipo.</span><span class="sxs-lookup"><span data-stu-id="4b25f-114">The following code lines show invalid declarations of this type.</span></span>  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a><span data-ttu-id="4b25f-115">Acceder a una matriz fuera de los límites</span><span class="sxs-lookup"><span data-stu-id="4b25f-115">Accessing an Array Out of Bounds</span></span>  
 <span data-ttu-id="4b25f-116">El proceso de inicialización de una matriz asigna un límite superior y un límite inferior a cada dimensión.</span><span class="sxs-lookup"><span data-stu-id="4b25f-116">The process of initializing an array assigns an upper bound and a lower bound to each dimension.</span></span> <span data-ttu-id="4b25f-117">Cada acceso a un elemento de la matriz debe especificar un índice válido, o subíndice, para cada dimensión.</span><span class="sxs-lookup"><span data-stu-id="4b25f-117">Every access to an element of the array must specify a valid index, or subscript, for every dimension.</span></span> <span data-ttu-id="4b25f-118">Si un índice está por debajo de su límite inferior o por encima de su límite superior, se <xref:System.IndexOutOfRangeException> produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="4b25f-118">If any index is below its lower bound or above its upper bound, an <xref:System.IndexOutOfRangeException> exception results.</span></span> <span data-ttu-id="4b25f-119">El compilador no puede detectar este tipo de error, por lo que se produce un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4b25f-119">The compiler cannot detect such an error, so an error occurs at run time.</span></span>  
  
### <a name="determining-bounds"></a><span data-ttu-id="4b25f-120">Determinar los límites</span><span class="sxs-lookup"><span data-stu-id="4b25f-120">Determining Bounds</span></span>  
 <span data-ttu-id="4b25f-121">Si otro componente pasa una matriz al código (por ejemplo, como un argumento de procedimiento), no se conoce el tamaño de la matriz o las longitudes de sus dimensiones.</span><span class="sxs-lookup"><span data-stu-id="4b25f-121">If another component passes an array to your code, for example as a procedure argument, you do not know the size of that array or the lengths of its dimensions.</span></span> <span data-ttu-id="4b25f-122">Siempre debe determinar el límite superior de cada dimensión de una matriz antes de intentar tener acceso a los elementos.</span><span class="sxs-lookup"><span data-stu-id="4b25f-122">You should always determine the upper bound for every dimension of an array before you attempt to access any elements.</span></span> <span data-ttu-id="4b25f-123">Si la matriz se ha creado por algunos medios distintos de una `New` cláusula Visual Basic, el límite inferior podría ser distinto de 0 y es más seguro determinar ese límite inferior también.</span><span class="sxs-lookup"><span data-stu-id="4b25f-123">If the array has been created by some means other than a Visual Basic `New` clause, the lower bound might be something other than 0, and it is safest to determine that lower bound as well.</span></span>  
  
### <a name="specifying-the-dimension"></a><span data-ttu-id="4b25f-124">Especificar la dimensión</span><span class="sxs-lookup"><span data-stu-id="4b25f-124">Specifying the Dimension</span></span>  
 <span data-ttu-id="4b25f-125">Al determinar los límites de una matriz multidimensional, tenga cuidado al especificar la dimensión.</span><span class="sxs-lookup"><span data-stu-id="4b25f-125">When determining the bounds of a multidimensional array, take care how you specify the dimension.</span></span> <span data-ttu-id="4b25f-126">Los `dimension` parámetros de los <xref:System.Array.GetLowerBound%2A> <xref:System.Array.GetUpperBound%2A> métodos y se basan en 0, mientras que los `Rank` parámetros de las <xref:Microsoft.VisualBasic.Information.LBound%2A> funciones Visual Basic y <xref:Microsoft.VisualBasic.Information.UBound%2A> se basan en 1.</span><span class="sxs-lookup"><span data-stu-id="4b25f-126">The `dimension` parameters of the <xref:System.Array.GetLowerBound%2A> and <xref:System.Array.GetUpperBound%2A> methods are 0-based, while the `Rank` parameters of the Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> and <xref:Microsoft.VisualBasic.Information.UBound%2A> functions are 1-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b25f-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b25f-127">See also</span></span>

- [<span data-ttu-id="4b25f-128">Matrices</span><span class="sxs-lookup"><span data-stu-id="4b25f-128">Arrays</span></span>](index.md)
- [<span data-ttu-id="4b25f-129">Cómo: Inicializar una variable de matriz en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4b25f-129">How to: Initialize an Array Variable in Visual Basic</span></span>](how-to-initialize-an-array-variable.md)
