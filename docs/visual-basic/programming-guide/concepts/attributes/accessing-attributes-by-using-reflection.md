---
description: Más información acerca de cómo obtener acceso a los atributos mediante la reflexión (Visual Basic)
title: Acceso a atributos mediante reflexión
ms.date: 07/20/2015
ms.assetid: c56e41da-5433-464f-a7bf-2a722e78bc9f
ms.openlocfilehash: e585bb427456f1187eaf8c39937eaa67651d9309
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100437870"
---
# <a name="accessing-attributes-by-using-reflection-visual-basic"></a><span data-ttu-id="c7988-103">Accessing Attributes by Using Reflection (Visual Basic) (Acceso a atributos mediante reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="c7988-103">Accessing Attributes by Using Reflection (Visual Basic)</span></span>

<span data-ttu-id="c7988-104">El hecho de que pueda definir atributos personalizados y colocarlos en el código fuente no serviría de mucho si no existiera ninguna forma de recuperar la información y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="c7988-104">The fact that you can define custom attributes and place them in your source code would be of little value without some way of retrieving that information and acting on it.</span></span> <span data-ttu-id="c7988-105">Mediante la reflexión, puede recuperar la información que se ha definido con atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="c7988-105">By using reflection, you can retrieve the information that was defined with custom attributes.</span></span> <span data-ttu-id="c7988-106">El método clave es `GetCustomAttributes`, que devuelve una matriz de objetos que son los equivalentes en tiempo de ejecución de los atributos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="c7988-106">The key method is `GetCustomAttributes`, which returns an array of objects that are the run-time equivalents of the source code attributes.</span></span> <span data-ttu-id="c7988-107">Este método tiene varias versiones sobrecargadas.</span><span class="sxs-lookup"><span data-stu-id="c7988-107">This method has several overloaded versions.</span></span> <span data-ttu-id="c7988-108">Para obtener más información, vea <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="c7988-108">For more information, see <xref:System.Attribute>.</span></span>

<span data-ttu-id="c7988-109">Una especificación de atributo como:</span><span class="sxs-lookup"><span data-stu-id="c7988-109">An attribute specification such as:</span></span>

```vb
<Author("P. Ackerman", Version:=1.1)>
Class SampleClass
    ' P. Ackerman's code goes here...
End Class
```

 <span data-ttu-id="c7988-110">es conceptualmente equivalente a esta:</span><span class="sxs-lookup"><span data-stu-id="c7988-110">is conceptually equivalent to this:</span></span>

```vb
Dim anonymousAuthorObject As Author = New Author("P. Ackerman")
anonymousAuthorObject.version = 1.1
```

<span data-ttu-id="c7988-111">En cambio, el código no se ejecuta hasta que se consulta a `SampleClass` sobre los atributos.</span><span class="sxs-lookup"><span data-stu-id="c7988-111">However, the code is not executed until `SampleClass` is queried for attributes.</span></span> <span data-ttu-id="c7988-112">Llamar a `GetCustomAttributes` en `SampleClass` hace que se cree e inicialice un objeto `Author` como se ha mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c7988-112">Calling `GetCustomAttributes` on `SampleClass` causes an `Author` object to be constructed and initialized as above.</span></span> <span data-ttu-id="c7988-113">Si la clase tiene otros atributos, se crean otros objetos de atributo de forma similar.</span><span class="sxs-lookup"><span data-stu-id="c7988-113">If the class has other attributes, other attribute objects are constructed similarly.</span></span> <span data-ttu-id="c7988-114">Luego, `GetCustomAttributes` devuelve el objeto `Author` y cualquier otro objeto de atributo en una matriz.</span><span class="sxs-lookup"><span data-stu-id="c7988-114">`GetCustomAttributes` then returns the `Author` object and any other attribute objects in an array.</span></span> <span data-ttu-id="c7988-115">Después, puede recorrer en iteración esta matriz, determinar qué atributos se han aplicado según el tipo de cada elemento de la matriz y extraer información de los objetos de atributo.</span><span class="sxs-lookup"><span data-stu-id="c7988-115">You can then iterate over this array, determine what attributes were applied based on the type of each array element, and extract information from the attribute objects.</span></span>

## <a name="example"></a><span data-ttu-id="c7988-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7988-116">Example</span></span>

<span data-ttu-id="c7988-117">Este es un ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="c7988-117">Here is a complete example.</span></span> <span data-ttu-id="c7988-118">Se define un atributo personalizado, se aplica a varias entidades y se recupera mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="c7988-118">A custom attribute is defined, applied to several entities, and retrieved via reflection.</span></span>

```vb
' Multiuse attribute
<System.AttributeUsage(System.AttributeTargets.Class Or
                       System.AttributeTargets.Struct,
                       AllowMultiple:=True)>
Public Class Author
    Inherits System.Attribute
    Private name As String
    Public version As Double
    Sub New(ByVal authorName As String)
        name = authorName

        ' Default value
        version = 1.0
    End Sub

    Function GetName() As String
        Return name
    End Function
End Class

' Class with the Author attribute
<Author("P. Ackerman")>
Public Class FirstClass
End Class

' Class without the Author attribute
Public Class SecondClass
End Class

' Class with multiple Author attributes.
<Author("P. Ackerman"), Author("R. Koch", Version:=2.0)>
Public Class ThirdClass
End Class

Class TestAuthorAttribute
    Sub Main()
        PrintAuthorInfo(GetType(FirstClass))
        PrintAuthorInfo(GetType(SecondClass))
        PrintAuthorInfo(GetType(ThirdClass))
    End Sub

    Private Shared Sub PrintAuthorInfo(ByVal t As System.Type)
        System.Console.WriteLine("Author information for {0}", t)

        ' Using reflection
        Dim attrs() As System.Attribute = System.Attribute.GetCustomAttributes(t)

        ' Displaying output
        For Each attr In attrs
            Dim a As Author = CType(attr, Author)
            System.Console.WriteLine("   {0}, version {1:f}", a.GetName(), a.version)
        Next
    End Sub

    ' Output:
    '   Author information for FirstClass
    '     P. Ackerman, version 1.00
    ' Author information for SecondClass
    ' Author information for ThirdClass
    '  R. Koch, version 2.00
    '  P. Ackerman, version 1.00

End Class
```

## <a name="see-also"></a><span data-ttu-id="c7988-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7988-119">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="c7988-120">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7988-120">Visual Basic Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="c7988-121">Recuperar información almacenada en atributos</span><span class="sxs-lookup"><span data-stu-id="c7988-121">Retrieving Information Stored in Attributes</span></span>](../../../../standard/attributes/retrieving-information-stored-in-attributes.md)
- <span data-ttu-id="c7988-122">[Reflection (Visual Basic)](../reflection.md) (Reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="c7988-122">[Reflection (Visual Basic)](../reflection.md)</span></span>
- [<span data-ttu-id="c7988-123">Atributos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7988-123">Attributes (Visual Basic)</span></span>](../../../language-reference/attributes.md)
- <span data-ttu-id="c7988-124">[Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md) (Creación de atributos personalizados [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="c7988-124">[Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md)</span></span>
