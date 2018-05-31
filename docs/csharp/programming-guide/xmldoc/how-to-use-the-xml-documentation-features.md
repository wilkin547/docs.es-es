---
title: 'Cómo: Utilizar las características de documentación XML (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: d7f1f51040033cf25f7f1aefb04d249e6e028ca3
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
ms.locfileid: "34472781"
---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="b5d08-102">Cómo: Utilizar las características de documentación XML (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b5d08-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="b5d08-103">En el ejemplo siguiente se proporciona una introducción básica de un tipo que se ha documentado.</span><span class="sxs-lookup"><span data-stu-id="b5d08-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5d08-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5d08-104">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  

<span data-ttu-id="b5d08-105">El ejemplo genera un archivo .xml con el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="b5d08-105">The example generates an .xml file with the following contents:</span></span>

```xml  
<?xml version="1.0"?>  
<doc>  
 <assembly>  
 <name>xmlsample</name>  
 </assembly>  
 <members>  
 <member name="T:SomeClass">  
 <summary>  
 Class level summary documentation goes here.</summary>  
 <remarks>  
 Longer comments can be associated with a type or member  
 through the remarks tag</remarks>  
 </member>  
 <member name="F:SomeClass.m_Name">  
 <summary>  
 Store for the name property</summary>  
 </member>  
 <member name="M:SomeClass.#ctor">  
 <summary>The class constructor.</summary>  
 </member>  
 <member name="M:SomeClass.SomeMethod(System.String)">  
 <summary>  
 Description for SomeMethod.</summary>  
 <param name="s"> Parameter description for s goes here</param>  
 <seealso cref="T:System.String">  
 You can use the cref attribute on any tag to reference a type or member  
 and the compiler will check that the reference exists. </seealso>  
 </member>  
 <member name="M:SomeClass.SomeOtherMethod">  
 <summary>  
 Some other method. </summary>  
 <returns>  
 Return results are described through the returns tag.</returns>  
 <seealso cref="M:SomeClass.SomeMethod(System.String)">  
 Notice the use of the cref attribute to reference a specific method </seealso>  
 </member>  
 <member name="M:SomeClass.Main(System.String[])">  
 <summary>  
 The entry point for the application.  
 </summary>  
 <param name="args"> A list of command line arguments</param>  
 </member>  
 <member name="P:SomeClass.Name">  
 <summary>  
 Name property </summary>  
 <value>A value tag is used to describe the property value</value>  
 </member>  
 </members>  
</doc>   
```

## <a name="compiling-the-code"></a><span data-ttu-id="b5d08-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b5d08-106">Compiling the Code</span></span>  
 <span data-ttu-id="b5d08-107">Para compilar el ejemplo, escriba la siguiente línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="b5d08-107">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="b5d08-108">Esto creará el archivo XML XMLsample.xml, que se puede ver en el explorador o mediante el comando TYPE.</span><span class="sxs-lookup"><span data-stu-id="b5d08-108">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b5d08-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="b5d08-109">Robust Programming</span></span>  
 <span data-ttu-id="b5d08-110">La documentación XML empieza con ///.</span><span class="sxs-lookup"><span data-stu-id="b5d08-110">XML documentation starts with ///.</span></span> <span data-ttu-id="b5d08-111">Cuando se crea un proyecto, el asistente agrega automáticamente unas líneas de inicio ///.</span><span class="sxs-lookup"><span data-stu-id="b5d08-111">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="b5d08-112">El procesamiento de estos comentarios tiene algunas restricciones:</span><span class="sxs-lookup"><span data-stu-id="b5d08-112">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="b5d08-113">La documentación debe ser XML con formato correcto.</span><span class="sxs-lookup"><span data-stu-id="b5d08-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="b5d08-114">Si el XML no tiene el formato correcto, se generará una advertencia y el archivo de documentación incluirá un comentario en el que se indica que se detectó un error.</span><span class="sxs-lookup"><span data-stu-id="b5d08-114">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="b5d08-115">Los desarrolladores pueden crear su propio conjunto de etiquetas,</span><span class="sxs-lookup"><span data-stu-id="b5d08-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="b5d08-116">Hay un conjunto de etiquetas recomendado (consulte [Etiquetas recomendadas para los comentarios de documentación](recommended-tags-for-documentation-comments.md)).</span><span class="sxs-lookup"><span data-stu-id="b5d08-116">There is a recommended set of tags (see [Recommended tags for documentation comments](recommended-tags-for-documentation-comments.md)).</span></span> <span data-ttu-id="b5d08-117">Algunas de las etiquetas recomendadas tienen significados especiales:</span><span class="sxs-lookup"><span data-stu-id="b5d08-117">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="b5d08-118">La etiqueta \<param> se usa para describir parámetros.</span><span class="sxs-lookup"><span data-stu-id="b5d08-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="b5d08-119">Si se usa, el compilador comprobará que el parámetro existe y que todos los parámetros se describen en la documentación.</span><span class="sxs-lookup"><span data-stu-id="b5d08-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="b5d08-120">Si se produce un error en la comprobación, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="b5d08-120">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="b5d08-121">El atributo `cref` se puede asociar a cualquier etiqueta para proporcionar una referencia a un elemento de código.</span><span class="sxs-lookup"><span data-stu-id="b5d08-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="b5d08-122">El compilador comprobará si existe ese elemento de código.</span><span class="sxs-lookup"><span data-stu-id="b5d08-122">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="b5d08-123">Si se produce un error en la comprobación, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="b5d08-123">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="b5d08-124">El compilador respeta todas las instrucciones `using` cuando busca un tipo descrito en el atributo `cref`.</span><span class="sxs-lookup"><span data-stu-id="b5d08-124">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="b5d08-125">IntelliSense usa la etiqueta \<summary> en Visual Studio para mostrar información adicional sobre un tipo o miembro.</span><span class="sxs-lookup"><span data-stu-id="b5d08-125">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b5d08-126">El archivo XML no proporciona información completa sobre los tipos y los miembros (por ejemplo, no contiene información de tipos).</span><span class="sxs-lookup"><span data-stu-id="b5d08-126">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="b5d08-127">Para obtener información completa sobre un tipo o miembro, debe usarse el archivo de documentación con reflexión en el tipo o miembro reales.</span><span class="sxs-lookup"><span data-stu-id="b5d08-127">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5d08-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5d08-128">See Also</span></span>  
 [<span data-ttu-id="b5d08-129">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b5d08-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b5d08-130">/doc (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="b5d08-130">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [<span data-ttu-id="b5d08-131">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="b5d08-131">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
