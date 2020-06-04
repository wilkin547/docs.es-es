---
title: Procedimiento para asignar una matriz a otra
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: c38def1ba9f3720bc760d6f6e4264510c884c930
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413084"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="188cf-102">Cómo: Asignar una matriz a otra (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="188cf-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>

<span data-ttu-id="188cf-103">Dado que las matrices son objetos, puede usarlas en instrucciones de asignación como otros tipos de objeto.</span><span class="sxs-lookup"><span data-stu-id="188cf-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="188cf-104">Una variable de matriz contiene un puntero a los datos que conforman los elementos de la matriz y la información de rango y longitud, y una asignación solo copia este puntero.</span><span class="sxs-lookup"><span data-stu-id="188cf-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>

### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="188cf-105">Para asignar una matriz a otra matriz</span><span class="sxs-lookup"><span data-stu-id="188cf-105">To assign one array to another array</span></span>

1. <span data-ttu-id="188cf-106">Asegúrese de que las dos matrices tienen el mismo rango (número de dimensiones) y tipos de datos de elementos compatibles.</span><span class="sxs-lookup"><span data-stu-id="188cf-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>

2. <span data-ttu-id="188cf-107">Use una instrucción de asignación estándar para asignar la matriz de origen a la matriz de destino.</span><span class="sxs-lookup"><span data-stu-id="188cf-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="188cf-108">No siga ningún nombre de matriz entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="188cf-108">Do not follow either array name with parentheses.</span></span>

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

<span data-ttu-id="188cf-109">Al asignar una matriz a otra, se aplican las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="188cf-109">When you assign one array to another, the following rules apply:</span></span>

- <span data-ttu-id="188cf-110">**Rangos iguales.**</span><span class="sxs-lookup"><span data-stu-id="188cf-110">**Equal Ranks.**</span></span> <span data-ttu-id="188cf-111">El rango (número de dimensiones) de la matriz de destino debe ser el mismo que el de la matriz de origen.</span><span class="sxs-lookup"><span data-stu-id="188cf-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>

  <span data-ttu-id="188cf-112">Siempre que los rangos de las dos matrices sean iguales, no es necesario que las dimensiones sean iguales.</span><span class="sxs-lookup"><span data-stu-id="188cf-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="188cf-113">El número de elementos de una dimensión determinada puede cambiar durante la asignación.</span><span class="sxs-lookup"><span data-stu-id="188cf-113">The number of elements in a given dimension can change during assignment.</span></span>

- <span data-ttu-id="188cf-114">**Tipos de elemento.**</span><span class="sxs-lookup"><span data-stu-id="188cf-114">**Element Types.**</span></span> <span data-ttu-id="188cf-115">Ambas matrices deben tener elementos de *tipo de referencia* o ambas matrices deben tener elementos de *tipo de valor* .</span><span class="sxs-lookup"><span data-stu-id="188cf-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="188cf-116">Para obtener más información, vea [tipos de valor y tipos de referencia](../data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="188cf-116">For more information, see [Value Types and Reference Types](../data-types/value-types-and-reference-types.md).</span></span>

  - <span data-ttu-id="188cf-117">Si ambas matrices tienen elementos de tipo de valor, los tipos de datos de los elementos deben ser exactamente iguales.</span><span class="sxs-lookup"><span data-stu-id="188cf-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="188cf-118">La única excepción a esto es que puede asignar una matriz de `Enum` elementos a una matriz del tipo base de ese `Enum` .</span><span class="sxs-lookup"><span data-stu-id="188cf-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>

  - <span data-ttu-id="188cf-119">Si ambas matrices tienen elementos de tipo de referencia, el tipo de elemento de origen debe derivar del tipo de elemento de destino.</span><span class="sxs-lookup"><span data-stu-id="188cf-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="188cf-120">En este caso, las dos matrices tienen la misma relación de herencia que sus elementos.</span><span class="sxs-lookup"><span data-stu-id="188cf-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="188cf-121">Esto se denomina *covarianza de matriz*.</span><span class="sxs-lookup"><span data-stu-id="188cf-121">This is called *array covariance*.</span></span>

<span data-ttu-id="188cf-122">El compilador notifica un error si se infringen las reglas anteriores, por ejemplo, si los tipos de datos no son compatibles o los rangos no son iguales.</span><span class="sxs-lookup"><span data-stu-id="188cf-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="188cf-123">Puede Agregar control de errores al código para asegurarse de que las matrices son compatibles antes de intentar una asignación.</span><span class="sxs-lookup"><span data-stu-id="188cf-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="188cf-124">También puede usar la palabra clave del [operador TryCast](../../../language-reference/operators/trycast-operator.md) si desea evitar que se produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="188cf-124">You can also use the [TryCast Operator](../../../language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="188cf-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="188cf-125">See also</span></span>

- [<span data-ttu-id="188cf-126">Matrices</span><span class="sxs-lookup"><span data-stu-id="188cf-126">Arrays</span></span>](index.md)
- [<span data-ttu-id="188cf-127">Solución de problemas de matrices</span><span class="sxs-lookup"><span data-stu-id="188cf-127">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
- [<span data-ttu-id="188cf-128">Instrucción Enum</span><span class="sxs-lookup"><span data-stu-id="188cf-128">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)
- [<span data-ttu-id="188cf-129">Conversiones de matriz</span><span class="sxs-lookup"><span data-stu-id="188cf-129">Array Conversions</span></span>](../data-types/array-conversions.md)
