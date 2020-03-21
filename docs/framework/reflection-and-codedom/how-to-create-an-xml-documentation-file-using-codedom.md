---
title: 'Cómo: Crear un archivo de documentación XML mediante CodeDOM'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CodeDOM, generating XML documentation
- XML documentation, creating using CodeDOM
- Code Document Object Model, generating XML documentation
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
ms.openlocfilehash: a0ccb469a43c3a21a76eaf24fa7ce7b490dd5c4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180519"
---
# <a name="how-to-create-an-xml-documentation-file-using-codedom"></a><span data-ttu-id="0f952-102">Cómo: Crear un archivo de documentación XML mediante CodeDOM</span><span class="sxs-lookup"><span data-stu-id="0f952-102">How to: Create an XML Documentation File Using CodeDOM</span></span>
<span data-ttu-id="0f952-103">Se puede usar CodeDOM para crear código que genere documentación XML.</span><span class="sxs-lookup"><span data-stu-id="0f952-103">CodeDOM can be used to create code that generates XML documentation.</span></span> <span data-ttu-id="0f952-104">El proceso implica crear el gráfico CodeDOM que contenga los comentarios de la documentación XML, generar el código y compilar el código generado con la opción del compilador que crea el archivo de documentación XML.</span><span class="sxs-lookup"><span data-stu-id="0f952-104">The process involves creating the CodeDOM graph that contains the XML documentation comments, generating the code, and compiling the generated code with the compiler option that creates the XML documentation output.</span></span>  
  
### <a name="to-create-a-codedom-graph-that-contains-xml-documentation-comments"></a><span data-ttu-id="0f952-105">Para crear un gráfico CodeDOM que contenga comentarios de la documentación XML</span><span class="sxs-lookup"><span data-stu-id="0f952-105">To create a CodeDOM graph that contains XML documentation comments</span></span>  
  
1. <span data-ttu-id="0f952-106">Cree una <xref:System.CodeDom.CodeCompileUnit> que contenga el gráfico CodeDOM para la aplicación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0f952-106">Create a <xref:System.CodeDom.CodeCompileUnit> containing the CodeDOM graph for the sample application.</span></span>  
  
2. <span data-ttu-id="0f952-107">Use el constructor <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> con el parámetro `docComment` establecido en `true` para crear los elementos y el texto de los comentarios de la documentación XML.</span><span class="sxs-lookup"><span data-stu-id="0f952-107">Use the <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> constructor with the `docComment` parameter set to `true` to create the XML documentation comment elements and text.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]
     [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]  
  
### <a name="to-generate-the-code-from-the-codecompileunit"></a><span data-ttu-id="0f952-108">Para generar el código a partir de la CodeCompileUnit</span><span class="sxs-lookup"><span data-stu-id="0f952-108">To generate the code from the CodeCompileUnit</span></span>  
  
1. <span data-ttu-id="0f952-109">Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> para generar el código y crear un archivo de código fuente que se va a compilar.</span><span class="sxs-lookup"><span data-stu-id="0f952-109">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code and create a source file to be compiled.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]
     [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]  
  
### <a name="to-compile-the-code-and-generate-the-documentation-file"></a><span data-ttu-id="0f952-110">Para compilar el código y generar el archivo de documentación</span><span class="sxs-lookup"><span data-stu-id="0f952-110">To compile the code and generate the documentation file</span></span>  
  
1. <span data-ttu-id="0f952-111">Agregue la opción del compilador **/doc** a la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> de un objeto <xref:System.CodeDom.Compiler.CompilerParameters> y pase el objeto al método <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> para crear el archivo de documentación XML cuando se compile el código.</span><span class="sxs-lookup"><span data-stu-id="0f952-111">Add the **/doc** compiler option to the <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> property of a <xref:System.CodeDom.Compiler.CompilerParameters> object and pass the object to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> method to create the XML documentation file when the code is compiled.</span></span>  
  
     [!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]
     [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="0f952-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f952-112">Example</span></span>  
 <span data-ttu-id="0f952-113">En el ejemplo de código siguiente se crea un gráfico CodeDOM con comentarios de la documentación, se genera un archivo de código a partir del gráfico, se compila el archivo y se crea un archivo de documentación XML asociado.</span><span class="sxs-lookup"><span data-stu-id="0f952-113">The following code example creates a CodeDOM graph with documentation comments, generates a code file from the graph, and compiles the file and creates an associated XML documentation file.</span></span>  
  
 [!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)]
 [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]  
  
 <span data-ttu-id="0f952-114">En el ejemplo de código se crea la siguiente documentación XML en el archivo HelloWorldDoc.xml.</span><span class="sxs-lookup"><span data-stu-id="0f952-114">The code example creates the following XML documentation in the HelloWorldDoc.xml file.</span></span>  
  
```xml  
<?xml version="1.0" ?>
<doc>  
  <assembly>  
    <name>HelloWorld</name>
  </assembly>  
  <members>  
    <member name="T:Samples.Class1">  
      <summary>  
        Create a Hello World application.
        <seealso cref="M:Samples.Class1.Main" />
      </summary>  
    </member>  
    <member name="M:Samples.Class1.Main">  
      <summary>  
        Main method for HelloWorld application.
        <para>Add a new paragraph to the description.</para>
      </summary>  
    </member>  
  </members>  
</doc>  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0f952-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="0f952-115">Compiling the Code</span></span>  
  
- <span data-ttu-id="0f952-116">En este ejemplo de código, el permiso `FullTrust` debe estar establecido para que se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="0f952-116">This code example requires the `FullTrust` permission set to execute successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f952-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0f952-117">See also</span></span>

- [<span data-ttu-id="0f952-118">Documentar el código con XML</span><span class="sxs-lookup"><span data-stu-id="0f952-118">Documenting Your Code with XML</span></span>](../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="0f952-119">Comentarios de documentación XML</span><span class="sxs-lookup"><span data-stu-id="0f952-119">XML Documentation Comments</span></span>](../../csharp/programming-guide/xmldoc/index.md)
- [<span data-ttu-id="0f952-120">Documentación de XML</span><span class="sxs-lookup"><span data-stu-id="0f952-120">XML Documentation</span></span>](/cpp/ide/xml-documentation-visual-cpp)
