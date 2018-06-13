---
title: 'Cómo: Determinar el tipo al que hace referencia una variable de objeto (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 0dfd4ed87b65f536802ae71cbc3de41e1c4f83af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651319"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="97ecd-102">Cómo: Determinar el tipo al que hace referencia una variable de objeto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97ecd-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>
<span data-ttu-id="97ecd-103">Una variable de objeto contiene un puntero a datos que están almacenados en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="97ecd-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="97ecd-104">Puede cambiar el tipo de datos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="97ecd-104">The type of that data can change during run time.</span></span> <span data-ttu-id="97ecd-105">En cualquier momento, puede usar el <xref:System.Type.GetTypeCode%2A> método para determinar el tipo de tiempo de ejecución actual, o la [del operador TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) para averiguar si este tipo en tiempo de ejecución es compatible con un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="97ecd-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="97ecd-106">Para determinar que el tipo exacto al que una variable de objeto actualmente hace referencia a</span><span class="sxs-lookup"><span data-stu-id="97ecd-106">To determine the exact type an object variable currently refers to</span></span>  
  
1.  <span data-ttu-id="97ecd-107">En la variable de objeto, llame a la <xref:System.Object.GetType%2A> método para recuperar un <xref:System.Type?displayProperty=nameWithType> objeto.</span><span class="sxs-lookup"><span data-stu-id="97ecd-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2.  <span data-ttu-id="97ecd-108">En el <xref:System.Type?displayProperty=nameWithType> clase, llame al método compartido <xref:System.Type.GetTypeCode%2A> para recuperar la <xref:System.TypeCode> valor de enumeración para el tipo del objeto.</span><span class="sxs-lookup"><span data-stu-id="97ecd-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     <span data-ttu-id="97ecd-109">Puede probar el <xref:System.TypeCode> valor de enumeración con cualquier miembros de enumeración son de interés, como `Double`.</span><span class="sxs-lookup"><span data-stu-id="97ecd-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="97ecd-110">Para determinar si un objeto es compatible con un tipo especificado el tipo de variable</span><span class="sxs-lookup"><span data-stu-id="97ecd-110">To determine whether an object variable's type is compatible with a specified type</span></span>  
  
-   <span data-ttu-id="97ecd-111">Use la `TypeOf` operador en combinación con la [operador Is](../../../../visual-basic/language-reference/operators/is-operator.md) para probar el objeto con un `TypeOf`... `Is` expresión.</span><span class="sxs-lookup"><span data-stu-id="97ecd-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     <span data-ttu-id="97ecd-112">El `TypeOf`... `Is` expresión devuelve `True` si el objeto de tiempo de ejecución Value de tipo es compatible con el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="97ecd-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>  
  
     <span data-ttu-id="97ecd-113">El criterio de compatibilidad depende de si el tipo especificado es una clase, estructura o interfaz.</span><span class="sxs-lookup"><span data-stu-id="97ecd-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="97ecd-114">En general, los tipos son compatibles si el objeto es del mismo tipo como, hereda de o implementa el tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="97ecd-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="97ecd-115">Para obtener más información, consulte [del operador TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="97ecd-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="97ecd-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="97ecd-116">Compiling the Code</span></span>  
 <span data-ttu-id="97ecd-117">Tenga en cuenta que el tipo especificado no puede ser una variable o expresión.</span><span class="sxs-lookup"><span data-stu-id="97ecd-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="97ecd-118">Debe ser el nombre de un tipo definido, como una clase, estructura o interfaz.</span><span class="sxs-lookup"><span data-stu-id="97ecd-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="97ecd-119">Esto incluye los tipos intrínsecos como `Integer` y `String`.</span><span class="sxs-lookup"><span data-stu-id="97ecd-119">This includes intrinsic types such as `Integer` and `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97ecd-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="97ecd-120">See Also</span></span>  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.GetTypeCode%2A>  
 <xref:System.TypeCode>  
 [<span data-ttu-id="97ecd-121">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="97ecd-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="97ecd-122">Valores de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="97ecd-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="97ecd-123">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="97ecd-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
