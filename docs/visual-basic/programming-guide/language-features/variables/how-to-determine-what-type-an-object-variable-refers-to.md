---
title: Procedimiento para determinar el tipo al que hace referencia una variable de objeto
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: d3224000f5958a8619e38c4d2f6dc5dbb275ad45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410495"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="ea3cc-102">Cómo: Determinar el tipo al que hace referencia una variable de objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea3cc-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>

<span data-ttu-id="ea3cc-103">Una variable de objeto contiene un puntero a los datos que se almacenan en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="ea3cc-104">El tipo de datos que pueden cambiar durante el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-104">The type of that data can change during run time.</span></span> <span data-ttu-id="ea3cc-105">En cualquier momento, puede usar el <xref:System.Type.GetTypeCode%2A> método para determinar el tipo en tiempo de ejecución actual o el [operador typeof](../../../language-reference/operators/typeof-operator.md) para averiguar si el tipo en tiempo de ejecución actual es compatible con un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="ea3cc-106">Para determinar el tipo exacto al que una variable de objeto hace referencia actualmente</span><span class="sxs-lookup"><span data-stu-id="ea3cc-106">To determine the exact type an object variable currently refers to</span></span>

1. <span data-ttu-id="ea3cc-107">En la variable de objeto, llame al <xref:System.Object.GetType%2A> método para recuperar un <xref:System.Type?displayProperty=nameWithType> objeto.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. <span data-ttu-id="ea3cc-108">En la <xref:System.Type?displayProperty=nameWithType> clase, llame al método compartido <xref:System.Type.GetTypeCode%2A> para recuperar el <xref:System.TypeCode> valor de enumeración para el tipo del objeto.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    <span data-ttu-id="ea3cc-109">Puede probar el <xref:System.TypeCode> valor de la enumeración con cualquier miembro de la enumeración que sea de interés, como `Double` .</span><span class="sxs-lookup"><span data-stu-id="ea3cc-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="ea3cc-110">Para determinar si el tipo de una variable de objeto es compatible con un tipo especificado</span><span class="sxs-lookup"><span data-stu-id="ea3cc-110">To determine whether an object variable's type is compatible with a specified type</span></span>

- <span data-ttu-id="ea3cc-111">Use el `TypeOf` operador junto con el [operador is](../../../language-reference/operators/is-operator.md) para probar el objeto con una `TypeOf` expresión... `Is` .</span><span class="sxs-lookup"><span data-stu-id="ea3cc-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    <span data-ttu-id="ea3cc-112">La `TypeOf` expresión... `Is` devuelve `True` si el tipo en tiempo de ejecución del objeto es compatible con el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>

    <span data-ttu-id="ea3cc-113">El criterio de compatibilidad depende de si el tipo especificado es una clase, una estructura o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="ea3cc-114">En general, los tipos son compatibles si el objeto es del mismo tipo que, hereda de o implementa el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="ea3cc-115">Para obtener más información, vea [operador typeof](../../../language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="ea3cc-115">For more information, see [TypeOf Operator](../../../language-reference/operators/typeof-operator.md).</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="ea3cc-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ea3cc-116">Compile the code</span></span>

<span data-ttu-id="ea3cc-117">Tenga en cuenta que el tipo especificado no puede ser una variable o una expresión.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="ea3cc-118">Debe ser el nombre de un tipo definido, como una clase, una estructura o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="ea3cc-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="ea3cc-119">Esto incluye tipos intrínsecos como `Integer` y `String` .</span><span class="sxs-lookup"><span data-stu-id="ea3cc-119">This includes intrinsic types such as `Integer` and `String`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea3cc-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea3cc-120">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="ea3cc-121">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="ea3cc-121">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="ea3cc-122">Valores de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="ea3cc-122">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="ea3cc-123">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="ea3cc-123">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
