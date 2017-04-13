---
title: "Generating and Compiling Source Code from a CodeDOM Graph | Microsoft Docs"
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
  - "code compilers"
  - "CodeDOM, generating source code"
  - "Code Document Object Model, graphs"
  - "templated code generation"
  - "source code, generating"
  - "dynamically representing source code"
  - "generating CodeDOM graphs"
  - "Code Document Object Model, generating source code"
  - "translating language to language"
  - "compiling assemblies"
  - "generating source code in multiple languages"
  - "graphing with CodeDOM"
  - "dynamic compilation"
  - "assemblies [.NET Framework], CodeDOM"
  - "source code generation"
  - "outputting source code by CodeDOM"
  - "code generators"
  - "compiling source code, multiple languages"
  - "CodeDOM, graphs"
ms.assetid: 6c864c8e-6dd3-4a65-ace0-36879d9a9c42
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# Generating and Compiling Source Code from a CodeDOM Graph
El espacio de nombres <xref:System.CodeDom.Compiler> proporciona interfaces para generar código fuente a partir de gráficos de objetos CodeDOM y para administrar la compilación con compiladores admitidos.  Un proveedor de código puede generar código fuente en un lenguaje de programación determinado de acuerdo con un gráfico CodeDOM.  Por lo general, una clase derivada de <xref:System.CodeDom.Compiler.CodeDomProvider> puede proporcionar métodos para generar y compilar código para el lenguaje admitido por el proveedor.  
  
## Usar un proveedor de código CodeDOM para generar código fuente  
 Para generar código fuente en un lenguaje determinado, es necesario un gráfico CodeDOM que represente la estructura del código fuente que se va a generar.  
  
 En el ejemplo siguiente se muestra cómo crear una instancia de <xref:Microsoft.CSharp.CSharpCodeProvider>.  
  
 [!code-cpp[CodeDomExample#21](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#21)]
 [!code-csharp[CodeDomExample#21](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#21)]
 [!code-vb[CodeDomExample#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#21)]  
  
 Por lo general, el gráfico para la compilación de código se encuentra en <xref:System.CodeDom.CodeCompileUnit>.  Para generar código para una unidad **CodeCompileUnit** que contenga un gráfico CodeDOM, llame al método <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> del proveedor de código.  Este método contiene un parámetro para un <xref:System.IO.TextWriter> que utiliza para generar el código fuente, por lo que a veces es necesario crear primero un **TextWriter** en el que se pueda escribir.  En el siguiente ejemplo se muestra la forma de generar código a partir de una unidad **CodeCompileUnit** y la forma de escribir el código generado en un archivo denominado HelloWorld.cs.  
  
 [!code-cpp[CodeDomExample#22](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#22)]
 [!code-csharp[CodeDomExample#22](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#22)]
 [!code-vb[CodeDomExample#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#22)]  
  
## Usar un proveedor de código CodeDOM para compilar ensamblados  
 **Invocar la compilación**  
  
 Para compilar un ensamblado mediante un proveedor CodeDom, es necesario disponer de código fuente para compilar en un lenguaje para el que se disponga de un compilador o bien disponer de un gráfico CodeDOM a partir del cual se pueda generar el código fuente que se va a compilar.  
  
 Si se está compilando a partir de un gráfico CodeDOM, pase la unidad <xref:System.CodeDom.CodeCompileUnit> que contiene el gráfico al método <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A> del proveedor de código.  Si dispone de un archivo de código fuente escrito en un lenguaje que el compilador puede entender, pase el nombre del archivo que contiene el código fuente al método <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> del proveedor CodeDom.  También puede pasar una cadena que contenga el código fuente escrito en un lenguaje que el compilador entienda al método <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A> del proveedor CodeDom.  
  
 **Configurar parámetros de compilación**  
  
 Todos los métodos de invocación de compilación estándar de un proveedor CodeDom disponen de un parámetro del tipo <xref:System.CodeDom.Compiler.CompilerParameters> que indica las opciones que se van a utilizar para la compilación.  
  
 Puede especificar un nombre de archivo para el ensamblado de salida en la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.OutputAssembly%2A> de **CompilerParameters**.  De lo contrario, se utilizará un nombre de archivo de salida predeterminado.  
  
 De forma predeterminada, se inicializa un nuevo parámetro **CompilerParameters** con la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.GenerateExecutable%2A> establecida en **false**.  Si está compilando un programa ejecutable, debe establecer la propiedad **GenerateExecutable** en **true**.  Si la propiedad **GenerateExecutable** se establece en **false**, el compilador generará una biblioteca de clases.  
  
 Si compila un ejecutable a partir de un gráfico CodeDOM, debe definir <xref:System.CodeDom.CodeEntryPointMethod> en el gráfico.  Si existen varios puntos de entrada de código, puede ser necesario establecer la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.MainClass%2A> de **CompilerParameters** en el nombre de la clase que define el punto de entrada que se va utilizar.  
  
 Para incluir información de depuración en un archivo ejecutable generado, establezca la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.IncludeDebugInformation%2A> en **true**.  
  
 Si el proyecto hace referencia a algún ensamblado, debe especificar los nombres de ensamblados como elementos de una colección <xref:System.Collections.Specialized.StringCollection> como propiedad <xref:System.CodeDom.Compiler.CompilerParameters.ReferencedAssemblies%2A> de los **CompilerParameters** utilizados al invocar la compilación.  
  
 Se puede compilar un ensamblado escrito en la memoria en lugar de en disco estableciendo la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.GenerateInMemory%2A> en **true**.  Si se genera un ensamblado en memoria, el código puede obtener una referencia al ensamblado generado desde la propiedad <xref:System.CodeDom.Compiler.CompilerResults.CompiledAssembly%2A> de una clase <xref:System.CodeDom.Compiler.CompilerResults>.  Si un ensamblado se escribe en disco, puede obtener la ruta de acceso al ensamblado generado a partir de la propiedad <xref:System.CodeDom.Compiler.CompilerResults.PathToAssembly%2A> de **CompilerResults**.  
  
 Para especificar una cadena personalizada de argumentos de línea de comandos que se utilizarán al invocar el proceso de compilación, establezca la cadena en la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A>.  
  
 Si se requiere un token de seguridad de Win32 para invocar al proceso de compilación, especifique el token en la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.UserToken%2A>.  
  
 Para vincular un archivo de recursos de Win32 al ensamblado compilado, especifique el nombre del archivo de recursos de Win32 en la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.Win32Resource%2A>.  
  
 Para especificar un nivel de advertencia en el que se detendrá la compilación, establezca la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.WarningLevel%2A> en un entero que represente el nivel de advertencia en el que se detendrá la compilación.  También se puede configurar el compilador para que detenga la compilación si se producen advertencias; para ello, establezca la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.TreatWarningsAsErrors%2A> en **true**.  
  
 En el siguiente ejemplo de código se muestra la forma de compilar un archivo de código fuente utilizando un proveedor CodeDom derivado de la clase <xref:System.CodeDom.Compiler.CodeDomProvider>.  
  
 [!code-cpp[CodeDomExample#23](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#23)]
 [!code-csharp[CodeDomExample#23](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#23)]
 [!code-vb[CodeDomExample#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#23)]  
  
## Compatibilidad inicial para lenguajes  
 .NET Framework proporciona compiladores y generadores de código para los siguientes idiomas: C\#, Visual Basic, C\+\+, y JScript.  La compatibilidad de CodeDOM se puede ampliar a otros idiomas implementando generadores y compiladores de código específicos.  
  
## Vea también  
 <xref:System.CodeDom>   
 <xref:System.CodeDom.Compiler>   
 [Dynamic Source Code Generation and Compilation](../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)   
 [Referencia rápida de CodeDOM](http://msdn.microsoft.com/es-es/c77b8bfd-0a32-4e36-b59a-4f687f32c524)