---
title: 'Procedimiento para usar las características de documentación XML: guía de programación de C#'
description: Aprenda a usar las características de documentación XML. Vea ejemplos de código y examine los recursos adicionales disponibles.
ms.date: 06/01/2018
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: 9ad2cfe62c70174eec9020ad4c8ce11608aca36d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380675"
---
# <a name="how-to-use-the-xml-documentation-features"></a><span data-ttu-id="00ef8-104">Procedimiento para usar las características de la documentación XML</span><span class="sxs-lookup"><span data-stu-id="00ef8-104">How to use the XML documentation features</span></span>

<span data-ttu-id="00ef8-105">En el ejemplo siguiente se proporciona una introducción básica de un tipo que se ha documentado.</span><span class="sxs-lookup"><span data-stu-id="00ef8-105">The following sample provides a basic overview of a type that has been documented.</span></span>

## <a name="example"></a><span data-ttu-id="00ef8-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00ef8-106">Example</span></span>

[!code-csharp[csProgGuideDocComments#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#15)]

<span data-ttu-id="00ef8-107">En el ejemplo se genera un archivo *.xml* con el contenido siguiente.</span><span class="sxs-lookup"><span data-stu-id="00ef8-107">The example generates an *.xml* file with the following contents.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xmlsample</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            <summary>
            Class level summary documentation goes here.
            </summary>
            <remarks>
            Longer comments can be associated with a type or member through
            the remarks tag.
            </remarks>
        </member>
        <member name="F:TestClass._name">
            <summary>
            Store for the Name property.
            </summary>
        </member>
        <member name="M:TestClass.#ctor">
            <summary>
            The class constructor.
            </summary>
        </member>
        <member name="P:TestClass.Name">
            <summary>
            Name property.
            </summary>
            <value>
            A value tag is used to describe the property value.
            </value>
        </member>
        <member name="M:TestClass.SomeMethod(System.String)">
            <summary>
            Description for SomeMethod.
            </summary>
            <param name="s"> Parameter description for s goes here.</param>
            <seealso cref="T:System.String">
            You can use the cref attribute on any tag to reference a type or member
            and the compiler will check that the reference exists.
            </seealso>
        </member>
        <member name="M:TestClass.SomeOtherMethod">
            <summary>
            Some other method.
            </summary>
            <returns>
            Return values are described through the returns tag.
            </returns>
            <seealso cref="M:TestClass.SomeMethod(System.String)">
            Notice the use of the cref attribute to reference a specific method.
            </seealso>
        </member>
        <member name="M:TestClass.Main(System.String[])">
            <summary>
            The entry point for the application.
            </summary>
            <param name="args"> A list of command line arguments.</param>
        </member>
        <member name="T:TestInterface">
            <summary>
            Documentation that describes the interface goes here.
            </summary>
            <remarks>
            Details about the interface go here.
            </remarks>
        </member>
        <member name="M:TestInterface.InterfaceMethod(System.Int32)">
            <summary>
            Documentation that describes the method goes here.
            </summary>
            <param name="n">
            Parameter n requires an integer argument.
            </param>
            <returns>
            The method returns an integer.
            </returns>
        </member>
    </members>
</doc>
```

## <a name="compiling-the-code"></a><span data-ttu-id="00ef8-108">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="00ef8-108">Compiling the code</span></span>

<span data-ttu-id="00ef8-109">Para compilar el ejemplo, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="00ef8-109">To compile the example, enter the following command:</span></span>

`csc XMLsample.cs /doc:XMLsample.xml`

<span data-ttu-id="00ef8-110">Este comando crea el archivo XML *XMLsample.xml*, que se puede ver en el explorador o mediante el comando `TYPE`.</span><span class="sxs-lookup"><span data-stu-id="00ef8-110">This command creates the XML file *XMLsample.xml*, which you can view in your browser or by using the `TYPE` command.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="00ef8-111">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="00ef8-111">Robust programming</span></span>

<span data-ttu-id="00ef8-112">La documentación XML empieza con `///`.</span><span class="sxs-lookup"><span data-stu-id="00ef8-112">XML documentation starts with `///`.</span></span> <span data-ttu-id="00ef8-113">Cuando se crea un proyecto, el asistente agrega automáticamente unas líneas de inicio `///`.</span><span class="sxs-lookup"><span data-stu-id="00ef8-113">When you create a new project, the wizards put some starter `///` lines in for you.</span></span> <span data-ttu-id="00ef8-114">El procesamiento de estos comentarios tiene algunas restricciones:</span><span class="sxs-lookup"><span data-stu-id="00ef8-114">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="00ef8-115">La documentación debe ser XML con formato correcto.</span><span class="sxs-lookup"><span data-stu-id="00ef8-115">The documentation must be well-formed XML.</span></span> <span data-ttu-id="00ef8-116">Si el XML no tiene el formato correcto, se generará una advertencia y el archivo de documentación incluirá un comentario en el que se indica que se detectó un error.</span><span class="sxs-lookup"><span data-stu-id="00ef8-116">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>

- <span data-ttu-id="00ef8-117">Los desarrolladores pueden crear su propio conjunto de etiquetas,</span><span class="sxs-lookup"><span data-stu-id="00ef8-117">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="00ef8-118">Hay un [conjunto recomendado de etiquetas](recommended-tags-for-documentation-comments.md).</span><span class="sxs-lookup"><span data-stu-id="00ef8-118">There is a [recommended set of tags](recommended-tags-for-documentation-comments.md).</span></span> <span data-ttu-id="00ef8-119">Algunas de las etiquetas recomendadas tienen significados especiales:</span><span class="sxs-lookup"><span data-stu-id="00ef8-119">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="00ef8-120">La etiqueta `<param>` se usa para describir parámetros.</span><span class="sxs-lookup"><span data-stu-id="00ef8-120">The `<param>` tag is used to describe parameters.</span></span> <span data-ttu-id="00ef8-121">Si se usa, el compilador comprueba que el parámetro existe y que todos los parámetros se describen en la documentación.</span><span class="sxs-lookup"><span data-stu-id="00ef8-121">If used, the compiler verifies that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="00ef8-122">Si se produce un error en la comprobación, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="00ef8-122">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="00ef8-123">El atributo `cref` se puede asociar a cualquier etiqueta para hacer referencia a un elemento de código.</span><span class="sxs-lookup"><span data-stu-id="00ef8-123">The `cref` attribute can be attached to any tag to reference a code element.</span></span> <span data-ttu-id="00ef8-124">El compilador comprueba si existe este elemento de código.</span><span class="sxs-lookup"><span data-stu-id="00ef8-124">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="00ef8-125">Si se produce un error en la comprobación, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="00ef8-125">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="00ef8-126">El compilador respeta todas las instrucciones `using` cuando busca un tipo descrito en el atributo `cref`.</span><span class="sxs-lookup"><span data-stu-id="00ef8-126">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="00ef8-127">IntelliSense usa la etiqueta `<summary>` en Visual Studio para mostrar información adicional sobre un tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="00ef8-127">The `<summary>` tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>

    > [!NOTE]
    > <span data-ttu-id="00ef8-128">El archivo XML no proporciona información completa sobre los tipos y los miembros (por ejemplo, no contiene información de tipos).</span><span class="sxs-lookup"><span data-stu-id="00ef8-128">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="00ef8-129">Para obtener información completa sobre un tipo o miembro, use el archivo de documentación con reflexión en el tipo o miembro reales.</span><span class="sxs-lookup"><span data-stu-id="00ef8-129">To get full information about a type or member, use the documentation file together with reflection on the actual type or member.</span></span>

## <a name="see-also"></a><span data-ttu-id="00ef8-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="00ef8-130">See also</span></span>

- [<span data-ttu-id="00ef8-131">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="00ef8-131">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="00ef8-132">-doc (opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="00ef8-132">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="00ef8-133">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="00ef8-133">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="00ef8-134">Procesador de documentación de DocFX</span><span class="sxs-lookup"><span data-stu-id="00ef8-134">DocFX documentation processor</span></span>](https://dotnet.github.io/docfx/)
- [<span data-ttu-id="00ef8-135">Procesador de documentación de Sandcastle</span><span class="sxs-lookup"><span data-stu-id="00ef8-135">Sandcastle documentation processor</span></span>](https://github.com/EWSoftware/SHFB)
