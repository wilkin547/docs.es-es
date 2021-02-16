---
description: 'Más información acerca de cómo: determinar el tipo al que hace referencia una variable de objeto (Visual Basic)'
title: Procedimiento para determinar el tipo al que hace referencia una variable de objeto
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 699a8c5c075fc923a61a66f617c255f193cd8797
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481927"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="ed091-103">Cómo: Determinar el tipo al que hace referencia una variable de objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed091-103">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>

<span data-ttu-id="ed091-104">Una variable de objeto contiene un puntero a los datos que se almacenan en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="ed091-104">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="ed091-105">El tipo de datos que pueden cambiar durante el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ed091-105">The type of that data can change during run time.</span></span> <span data-ttu-id="ed091-106">En cualquier momento, puede usar el <xref:System.Type.GetTypeCode%2A> método para determinar el tipo en tiempo de ejecución actual o el [operador typeof](../../../language-reference/operators/typeof-operator.md) para averiguar si el tipo en tiempo de ejecución actual es compatible con un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="ed091-106">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="ed091-107">Para determinar el tipo exacto al que una variable de objeto hace referencia actualmente</span><span class="sxs-lookup"><span data-stu-id="ed091-107">To determine the exact type an object variable currently refers to</span></span>

1. <span data-ttu-id="ed091-108">En la variable de objeto, llame al <xref:System.Object.GetType%2A> método para recuperar un <xref:System.Type?displayProperty=nameWithType> objeto.</span><span class="sxs-lookup"><span data-stu-id="ed091-108">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. <span data-ttu-id="ed091-109">En la <xref:System.Type?displayProperty=nameWithType> clase, llame al método compartido <xref:System.Type.GetTypeCode%2A> para recuperar el <xref:System.TypeCode> valor de enumeración para el tipo del objeto.</span><span class="sxs-lookup"><span data-stu-id="ed091-109">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    <span data-ttu-id="ed091-110">Puede probar el <xref:System.TypeCode> valor de la enumeración con cualquier miembro de la enumeración que sea de interés, como `Double` .</span><span class="sxs-lookup"><span data-stu-id="ed091-110">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="ed091-111">Para determinar si el tipo de una variable de objeto es compatible con un tipo especificado</span><span class="sxs-lookup"><span data-stu-id="ed091-111">To determine whether an object variable's type is compatible with a specified type</span></span>

- <span data-ttu-id="ed091-112">Use el `TypeOf` operador junto con el [operador is](../../../language-reference/operators/is-operator.md) para probar el objeto con una `TypeOf` expresión... `Is` .</span><span class="sxs-lookup"><span data-stu-id="ed091-112">Use the `TypeOf` operator in combination with the [Is Operator](../../../language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    <span data-ttu-id="ed091-113">La `TypeOf` expresión... `Is` devuelve `True` si el tipo en tiempo de ejecución del objeto es compatible con el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="ed091-113">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>

    <span data-ttu-id="ed091-114">El criterio de compatibilidad depende de si el tipo especificado es una clase, una estructura o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="ed091-114">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="ed091-115">En general, los tipos son compatibles si el objeto es del mismo tipo que, hereda de o implementa el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="ed091-115">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="ed091-116">Para obtener más información, vea [operador typeof](../../../language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="ed091-116">For more information, see [TypeOf Operator](../../../language-reference/operators/typeof-operator.md).</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="ed091-117">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ed091-117">Compile the code</span></span>

<span data-ttu-id="ed091-118">Tenga en cuenta que el tipo especificado no puede ser una variable o una expresión.</span><span class="sxs-lookup"><span data-stu-id="ed091-118">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="ed091-119">Debe ser el nombre de un tipo definido, como una clase, una estructura o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="ed091-119">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="ed091-120">Esto incluye tipos intrínsecos como `Integer` y `String` .</span><span class="sxs-lookup"><span data-stu-id="ed091-120">This includes intrinsic types such as `Integer` and `String`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed091-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed091-121">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="ed091-122">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="ed091-122">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="ed091-123">Valores de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="ed091-123">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="ed091-124">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="ed091-124">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
