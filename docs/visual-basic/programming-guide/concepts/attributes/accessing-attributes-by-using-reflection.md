---
title: Acceso a atributos mediante reflexión
ms.date: 07/20/2015
ms.assetid: c56e41da-5433-464f-a7bf-2a722e78bc9f
ms.openlocfilehash: c0da5c4ae00eb2bc80b10f63f4bfd39763445e55
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400763"
---
# <a name="accessing-attributes-by-using-reflection-visual-basic"></a><span data-ttu-id="ba602-102">Accessing Attributes by Using Reflection (Visual Basic) (Acceso a atributos mediante reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="ba602-102">Accessing Attributes by Using Reflection (Visual Basic)</span></span>

<span data-ttu-id="ba602-103">El hecho de que pueda definir atributos personalizados y colocarlos en el código fuente no serviría de mucho si no existiera ninguna forma de recuperar la información y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="ba602-103">The fact that you can define custom attributes and place them in your source code would be of little value without some way of retrieving that information and acting on it.</span></span> <span data-ttu-id="ba602-104">Mediante la reflexión, puede recuperar la información que se ha definido con atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="ba602-104">By using reflection, you can retrieve the information that was defined with custom attributes.</span></span> <span data-ttu-id="ba602-105">El método clave es `GetCustomAttributes`, que devuelve una matriz de objetos que son los equivalentes en tiempo de ejecución de los atributos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="ba602-105">The key method is `GetCustomAttributes`, which returns an array of objects that are the run-time equivalents of the source code attributes.</span></span> <span data-ttu-id="ba602-106">Este método tiene varias versiones sobrecargadas.</span><span class="sxs-lookup"><span data-stu-id="ba602-106">This method has several overloaded versions.</span></span> <span data-ttu-id="ba602-107">Para obtener más información, consulta <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="ba602-107">For more information, see <xref:System.Attribute>.</span></span>

<span data-ttu-id="ba602-108">Una especificación de atributo como:</span><span class="sxs-lookup"><span data-stu-id="ba602-108">An attribute specification such as:</span></span>

```vb
<Author("P. Ackerman", Version:=1.1)>
Class SampleClass
    ' P. Ackerman's code goes here...
End Class
```

 <span data-ttu-id="ba602-109">es conceptualmente equivalente a esta:</span><span class="sxs-lookup"><span data-stu-id="ba602-109">is conceptually equivalent to this:</span></span>

```vb
Dim anonymousAuthorObject As Author = New Author("P. Ackerman")
anonymousAuthorObject.version = 1.1
```

<span data-ttu-id="ba602-110">En cambio, el código no se ejecuta hasta que se consulta a `SampleClass` sobre los atributos.</span><span class="sxs-lookup"><span data-stu-id="ba602-110">However, the code is not executed until `SampleClass` is queried for attributes.</span></span> <span data-ttu-id="ba602-111">Llamar a `GetCustomAttributes` en `SampleClass` hace que se cree e inicialice un objeto `Author` como se ha mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ba602-111">Calling `GetCustomAttributes` on `SampleClass` causes an `Author` object to be constructed and initialized as above.</span></span> <span data-ttu-id="ba602-112">Si la clase tiene otros atributos, se crean otros objetos de atributo de forma similar.</span><span class="sxs-lookup"><span data-stu-id="ba602-112">If the class has other attributes, other attribute objects are constructed similarly.</span></span> <span data-ttu-id="ba602-113">Luego, `GetCustomAttributes` devuelve el objeto `Author` y cualquier otro objeto de atributo en una matriz.</span><span class="sxs-lookup"><span data-stu-id="ba602-113">`GetCustomAttributes` then returns the `Author` object and any other attribute objects in an array.</span></span> <span data-ttu-id="ba602-114">Después, puede recorrer en iteración esta matriz, determinar qué atributos se han aplicado según el tipo de cada elemento de la matriz y extraer información de los objetos de atributo.</span><span class="sxs-lookup"><span data-stu-id="ba602-114">You can then iterate over this array, determine what attributes were applied based on the type of each array element, and extract information from the attribute objects.</span></span>

## <a name="example"></a><span data-ttu-id="ba602-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba602-115">Example</span></span>

<span data-ttu-id="ba602-116">Este es un ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="ba602-116">Here is a complete example.</span></span> <span data-ttu-id="ba602-117">Se define un atributo personalizado, se aplica a varias entidades y se recupera mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="ba602-117">A custom attribute is defined, applied to several entities, and retrieved via reflection.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ba602-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba602-118">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="ba602-119">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ba602-119">Visual Basic Programming Guide</span></span>](../../index.md)
- <span data-ttu-id="ba602-120">[Retrieving Information Stored in Attributes](../../../../standard/attributes/retrieving-information-stored-in-attributes.md) (Recuperar la información almacenada en atributos)</span><span class="sxs-lookup"><span data-stu-id="ba602-120">[Retrieving Information Stored in Attributes](../../../../standard/attributes/retrieving-information-stored-in-attributes.md)</span></span>
- <span data-ttu-id="ba602-121">[Reflection (Visual Basic)](../reflection.md) (Reflexión [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="ba602-121">[Reflection (Visual Basic)](../reflection.md)</span></span>
- [<span data-ttu-id="ba602-122">Atributos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba602-122">Attributes (Visual Basic)</span></span>](../../../language-reference/attributes.md)
- <span data-ttu-id="ba602-123">[Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md) (Creación de atributos personalizados [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="ba602-123">[Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md)</span></span>
