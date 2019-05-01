---
title: Procedimiento Asignar una matriz a otra (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: 78497de3a9aea55320639c55a151a1260a960159
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053683"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="851a3-102">Procedimiento Asignar una matriz a otra (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="851a3-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>

<span data-ttu-id="851a3-103">Dado que las matrices son objetos, se puede usar en instrucciones de asignación como otros tipos de objeto.</span><span class="sxs-lookup"><span data-stu-id="851a3-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="851a3-104">Una variable de matriz contiene un puntero a los datos que constituyen los elementos de matriz y la información de rango y la longitud y la copia de una asignación de puntero this.</span><span class="sxs-lookup"><span data-stu-id="851a3-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>

### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="851a3-105">Para asignar una matriz a otra</span><span class="sxs-lookup"><span data-stu-id="851a3-105">To assign one array to another array</span></span>

1. <span data-ttu-id="851a3-106">Asegúrese de que las dos matrices tienen el mismo rango (número de dimensiones) y tipos de datos de elemento compatibles.</span><span class="sxs-lookup"><span data-stu-id="851a3-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>

2. <span data-ttu-id="851a3-107">Usar una instrucción de asignación estándar para asignar la matriz de origen a la matriz de destino.</span><span class="sxs-lookup"><span data-stu-id="851a3-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="851a3-108">No siga cualquier nombre de la matriz con paréntesis.</span><span class="sxs-lookup"><span data-stu-id="851a3-108">Do not follow either array name with parentheses.</span></span>

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

<span data-ttu-id="851a3-109">Al asignar una matriz a otra, se aplican las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="851a3-109">When you assign one array to another, the following rules apply:</span></span>

- <span data-ttu-id="851a3-110">**Rangos iguales.**</span><span class="sxs-lookup"><span data-stu-id="851a3-110">**Equal Ranks.**</span></span> <span data-ttu-id="851a3-111">El rango (número de dimensiones) de la matriz de destino debe ser el mismo que el de la matriz de origen.</span><span class="sxs-lookup"><span data-stu-id="851a3-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>

  <span data-ttu-id="851a3-112">Los rangos de las dos matrices son iguales, las dimensiones no es necesario para que sea igual.</span><span class="sxs-lookup"><span data-stu-id="851a3-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="851a3-113">Puede cambiar el número de elementos de una dimensión determinada durante la asignación.</span><span class="sxs-lookup"><span data-stu-id="851a3-113">The number of elements in a given dimension can change during assignment.</span></span>

- <span data-ttu-id="851a3-114">**Tipos de elemento.**</span><span class="sxs-lookup"><span data-stu-id="851a3-114">**Element Types.**</span></span> <span data-ttu-id="851a3-115">Deben tener ambas matrices *tipo de referencia* elementos o ambas matrices deben tener *tipo de valor* elementos.</span><span class="sxs-lookup"><span data-stu-id="851a3-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="851a3-116">Para obtener más información, consulta [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="851a3-116">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>

  - <span data-ttu-id="851a3-117">Si ambas matrices tienen elementos de tipo de valor, los tipos de elemento de datos deben ser exactamente el mismo.</span><span class="sxs-lookup"><span data-stu-id="851a3-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="851a3-118">La única excepción a esto es que puede asignar una matriz de `Enum` elementos en una matriz del tipo base del que `Enum`.</span><span class="sxs-lookup"><span data-stu-id="851a3-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>

  - <span data-ttu-id="851a3-119">Si ambas matrices tienen la referencia de elementos de tipo, el tipo de elemento de origen debe derivar del tipo de elemento de destino.</span><span class="sxs-lookup"><span data-stu-id="851a3-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="851a3-120">Cuando esto sucede, las dos matrices tienen la misma relación de herencia que sus elementos.</span><span class="sxs-lookup"><span data-stu-id="851a3-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="851a3-121">Esto se denomina *covarianza de matrices*.</span><span class="sxs-lookup"><span data-stu-id="851a3-121">This is called *array covariance*.</span></span>

<span data-ttu-id="851a3-122">El compilador notifica un error si se infringen las reglas anteriores, por ejemplo si los tipos de datos no son compatibles o los rangos no son iguales.</span><span class="sxs-lookup"><span data-stu-id="851a3-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="851a3-123">Puede agregar el código para asegurarse de que las matrices son compatibles antes de intentar una asignación de control de errores.</span><span class="sxs-lookup"><span data-stu-id="851a3-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="851a3-124">También puede usar el [TryCast (operador)](../../../../visual-basic/language-reference/operators/trycast-operator.md) palabra clave si desea evitar que se produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="851a3-124">You can also use the [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="851a3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="851a3-125">See also</span></span>

- [<span data-ttu-id="851a3-126">Matrices</span><span class="sxs-lookup"><span data-stu-id="851a3-126">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="851a3-127">Solución de problemas de matrices</span><span class="sxs-lookup"><span data-stu-id="851a3-127">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [<span data-ttu-id="851a3-128">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="851a3-128">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="851a3-129">Conversiones de matriz</span><span class="sxs-lookup"><span data-stu-id="851a3-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
