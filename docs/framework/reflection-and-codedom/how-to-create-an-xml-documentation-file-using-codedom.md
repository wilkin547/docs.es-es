---
title: "How to: Create an XML Documentation File Using CodeDOM | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CodeDOM, generating XML documentation"
  - "XML documentation, creating using CodeDOM"
  - "Code Document Object Model, generating XML documentation"
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Create an XML Documentation File Using CodeDOM
CodeDOM se puede utilizar para crear código que genera documentación XML.  El proceso implica crear el gráfico CodeDOM que contiene los comentarios de la documentación XML, generar el código y compilar el código generado con la opción del compilador que crea la documentación XML generada.  
  
### Para crear un gráfico CodeDOM que contiene comentarios de la documentación XML  
  
1.  Cree un <xref:System.CodeDom.CodeCompileUnit> que contenga el gráfico CodeDOM para la aplicación de ejemplo.  
  
2.  Utilice el constructor <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> con el parámetro `docComment` establecido en `true` para crear el texto y los elementos de comentario de la documentación XML.  
  
     [!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]
     [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]  
  
### Para generar el código de CodeCompileUnit  
  
1.  Utilice el método <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> para generar el código y crear un archivo de código fuente que se va a compilar.  
  
     [!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]
     [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]  
  
### Compilar el código y generar el archivo de documentación  
  
1.  Agregue la opción del compilador **\/doc** a la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> de un objeto <xref:System.CodeDom.Compiler.CompilerParameters> y pase el objeto al método <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> para crear el archivo de documentación XML cuando se compile el código.  
  
     [!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]
     [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]  
  
## Ejemplo  
 El ejemplo de código siguiente crea un gráfico CodeDOM con comentarios de la documentación, genera un archivo de código del gráfico y compila el archivo y crea un archivo de documentación XML asociado.  
  
 [!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)]
 [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]  
  
 El ejemplo de código crea la siguiente documentación XML en el archivo HelloWorldDoc.xml.  
  
```  
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
  
## Compilar el código  
  
-   Este ejemplo de código exige que el conjunto de permisos `FullTrust` se ejecute correctamente.  
  
## Vea también  
 [Documentar el código con XML](../Topic/Documenting%20Your%20Code%20with%20XML%20\(Visual%20Basic\).md)   
 [Comentarios de documentación XML](../Topic/XML%20Documentation%20Comments%20\(C%23%20Programming%20Guide\).md)   
 [Documentación de XML](../Topic/XML%20Documentation%20\(Visual%20C++\).md)