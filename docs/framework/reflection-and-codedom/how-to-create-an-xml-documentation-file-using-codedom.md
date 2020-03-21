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
# <a name="how-to-create-an-xml-documentation-file-using-codedom"></a>Cómo: Crear un archivo de documentación XML mediante CodeDOM
Se puede usar CodeDOM para crear código que genere documentación XML. El proceso implica crear el gráfico CodeDOM que contenga los comentarios de la documentación XML, generar el código y compilar el código generado con la opción del compilador que crea el archivo de documentación XML.  
  
### <a name="to-create-a-codedom-graph-that-contains-xml-documentation-comments"></a>Para crear un gráfico CodeDOM que contenga comentarios de la documentación XML  
  
1. Cree una <xref:System.CodeDom.CodeCompileUnit> que contenga el gráfico CodeDOM para la aplicación de ejemplo.  
  
2. Use el constructor <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> con el parámetro `docComment` establecido en `true` para crear los elementos y el texto de los comentarios de la documentación XML.  
  
     [!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]
     [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]  
  
### <a name="to-generate-the-code-from-the-codecompileunit"></a>Para generar el código a partir de la CodeCompileUnit  
  
1. Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> para generar el código y crear un archivo de código fuente que se va a compilar.  
  
     [!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]
     [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]  
  
### <a name="to-compile-the-code-and-generate-the-documentation-file"></a>Para compilar el código y generar el archivo de documentación  
  
1. Agregue la opción del compilador **/doc** a la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> de un objeto <xref:System.CodeDom.Compiler.CompilerParameters> y pase el objeto al método <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> para crear el archivo de documentación XML cuando se compile el código.  
  
     [!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]
     [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se crea un gráfico CodeDOM con comentarios de la documentación, se genera un archivo de código a partir del gráfico, se compila el archivo y se crea un archivo de documentación XML asociado.  
  
 [!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)]
 [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]  
  
 En el ejemplo de código se crea la siguiente documentación XML en el archivo HelloWorldDoc.xml.  
  
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
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- En este ejemplo de código, el permiso `FullTrust` debe estar establecido para que se ejecute correctamente.  
  
## <a name="see-also"></a>Consulte también

- [Documentar el código con XML](../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [Comentarios de documentación XML](../../csharp/programming-guide/xmldoc/index.md)
- [Documentación de XML](/cpp/ide/xml-documentation-visual-cpp)
