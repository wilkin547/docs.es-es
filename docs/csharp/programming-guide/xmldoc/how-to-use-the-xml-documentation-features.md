---
title: 'Procedimiento para usar las características de documentación XML: Guía de programación de C#'
ms.date: 06/01/2018
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: 5de94b1f1ab44f954b5bab9f8b5212c33325c19d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75696719"
---
# <a name="how-to-use-the-xml-documentation-features"></a><span data-ttu-id="8ad7b-102">Procedimiento para usar las características de la documentación XML</span><span class="sxs-lookup"><span data-stu-id="8ad7b-102">How to use the XML documentation features</span></span>

<span data-ttu-id="8ad7b-103">En el ejemplo siguiente se proporciona una introducción básica de un tipo que se ha documentado.</span><span class="sxs-lookup"><span data-stu-id="8ad7b-103">The following sample provides a basic overview of a type that has been documented.</span></span>

## <a name="example"></a><span data-ttu-id="8ad7b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ad7b-104">Example</span></span>

[!code-csharp[csProgGuideDocComments#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#15)]

<span data-ttu-id="8ad7b-105">El ejemplo genera un archivo .xml con el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="8ad7b-105">The example generates an .xml file with the following contents:</span></span>

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

## <a name="compiling-the-code"></a><span data-ttu-id="8ad7b-106">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="8ad7b-106">Compiling the code</span></span>

<span data-ttu-id="8ad7b-107">Para compilar el ejemplo, escriba la siguiente línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="8ad7b-107">To compile the example, type the following command line:</span></span>

`csc XMLsample.cs /doc:XMLsample.xml`

<span data-ttu-id="8ad7b-108">Este comando crea el archivo XML *XMLsample.xml*, que se puede ver en el explorador o mediante el comando TYPE.</span><span class="sxs-lookup"><span data-stu-id="8ad7b-108">This command creates the XML file *XMLsample.xml*, which you can view in your browser or by using the TYPE command.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="8ad7b-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="8ad7b-109">Robust programming</span></span>

<span data-ttu-id="8ad7b-110">La documentación XML empieza con ///.</span><span class="sxs-lookup"><span data-stu-id="8ad7b-110">XML documentation starts with ///.</span></span> <span data-ttu-id="8ad7b-111">Cuando se crea un proyecto, el asistente agrega automáticamente unas líneas de inicio ///.</span><span class="sxs-lookup"><span data-stu-id="8ad7b-111">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="8ad7b-112">El procesamiento de estos comentarios tiene algunas restricciones:</span><span class="sxs-lookup"><span data-stu-id="8ad7b-112">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="8ad7b-113">La documentación debe ser XML con formato correcto.</span><span class="sxs-lookup"><span data-stu-id="8ad7b-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="8ad7b-114">Si el XML no tiene el formato correcto, se generará una advertencia y el archivo de documentación incluirá un comentario en el que se indica que se detectó un error.</span><span class="sxs-lookup"><span data-stu-id="8ad7b-114">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>

- <span data-ttu-id="8ad7b-115">Los desarrolladores pueden crear su propio conjunto de etiquetas,</span><span class="sxs-lookup"><span data-stu-id="8ad7b-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="8ad7b-116">Hay un conjunto de etiquetas recomendado (consulte [Etiquetas recomendadas para los comentarios de documentación](recommended-tags-for-documentation-comments.md)).</span><span class="sxs-lookup"><span data-stu-id="8ad7b-116">There is a recommended set of tags (see [Recommended tags for documentation comments](recommended-tags-for-documentation-comments.md)).</span></span> <span data-ttu-id="8ad7b-117">Algunas de las etiquetas recomendadas tienen significados especiales:</span><span class="sxs-lookup"><span data-stu-id="8ad7b-117">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="8ad7b-118">La etiqueta \<param> se usa para describir parámetros.</span><span class="sxs-lookup"><span data-stu-id="8ad7b-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="8ad7b-119">Si se usa, el compilador comprueba que el parámetro existe y que todos los parámetros se describen en la documentación.</span><span class="sxs-lookup"><span data-stu-id="8ad7b-119">If used, the compiler verifies that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="8ad7b-120">Si se produce un error en la comprobación, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="8ad7b-120">If the verification failed, the compiler issues a warning.</span></span>

  - <span data-ttu-id="8ad7b-121">El atributo `cref` se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código.</span><span class="sxs-lookup"><span data-stu-id="8ad7b-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="8ad7b-122">El compilador comprueba si existe este elemento de código.</span><span class="sxs-lookup"><span data-stu-id="8ad7b-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="8ad7b-123">Si se produce un error en la comprobación, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="8ad7b-123">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="8ad7b-124">El compilador respeta todas las instrucciones `using` cuando busca un tipo descrito en el atributo `cref`.</span><span class="sxs-lookup"><span data-stu-id="8ad7b-124">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="8ad7b-125">IntelliSense usa la etiqueta \<summary> en Visual Studio para mostrar información adicional sobre un tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="8ad7b-125">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8ad7b-126">El archivo XML no proporciona información completa sobre los tipos y los miembros (por ejemplo, no contiene información de tipos).</span><span class="sxs-lookup"><span data-stu-id="8ad7b-126">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="8ad7b-127">Para obtener información completa sobre un tipo o miembro, debe usarse el archivo de documentación con reflexión en el tipo o miembro reales.</span><span class="sxs-lookup"><span data-stu-id="8ad7b-127">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ad7b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ad7b-128">See also</span></span>

- [<span data-ttu-id="8ad7b-129">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8ad7b-129">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8ad7b-130">-doc (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="8ad7b-130">-doc (C# Compiler Options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="8ad7b-131">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="8ad7b-131">XML Documentation Comments</span></span>](./index.md)
- [<span data-ttu-id="8ad7b-132">Procesador de documentación de DocFX</span><span class="sxs-lookup"><span data-stu-id="8ad7b-132">DocFX documentation processor</span></span>](https://dotnet.github.io/docfx/)
- [<span data-ttu-id="8ad7b-133">Procesador de documentación de Sandcastle</span><span class="sxs-lookup"><span data-stu-id="8ad7b-133">Sandcastle documentation processor</span></span>](https://github.com/EWSoftware/SHFB)
