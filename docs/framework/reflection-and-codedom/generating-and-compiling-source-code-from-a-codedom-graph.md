---
title: Generar y compilar código fuente a partir de un gráfico CodeDOM
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- code compilers
- CodeDOM, generating source code
- Code Document Object Model, graphs
- templated code generation
- source code, generating
- dynamically representing source code
- generating CodeDOM graphs
- Code Document Object Model, generating source code
- translating language to language
- compiling assemblies
- generating source code in multiple languages
- graphing with CodeDOM
- dynamic compilation
- assemblies [.NET Framework], CodeDOM
- source code generation
- outputting source code by CodeDOM
- code generators
- compiling source code, multiple languages
- CodeDOM, graphs
ms.assetid: 6c864c8e-6dd3-4a65-ace0-36879d9a9c42
ms.openlocfilehash: a8d3bf7363cb887834a1c251aead05c75e2e3fe8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130222"
---
# <a name="generating-and-compiling-source-code-from-a-codedom-graph"></a>Generar y compilar código fuente a partir de un gráfico CodeDOM
El espacio de nombres <xref:System.CodeDom.Compiler> proporciona interfaces para generar código fuente a partir de gráficos de objetos CodeDOM y para administrar la compilación con compiladores compatibles. Un proveedor de código puede generar código fuente en un lenguaje de programación determinado según un gráfico CodeDOM. Una clase que deriva de <xref:System.CodeDom.Compiler.CodeDomProvider> normalmente puede proporcionar métodos para generar y compilar código para el lenguaje admitido por el proveedor.  
  
## <a name="using-a-codedom-code-provider-to-generate-source-code"></a>Uso de un proveedor de código CodeDOM para generar el código fuente  
 Para generar código fuente en un lenguaje determinado, se necesita un gráfico CodeDOM que represente la estructura del código fuente que se va a generar.  
  
 En el ejemplo siguiente se muestra cómo crear una instancia de <xref:Microsoft.CSharp.CSharpCodeProvider>:  
  
 [!code-cpp[CodeDomExample#21](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#21)]
 [!code-csharp[CodeDomExample#21](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#21)]
 [!code-vb[CodeDomExample#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#21)]  
  
 El gráfico para la generación de código normalmente se encuentra en un elemento <xref:System.CodeDom.CodeCompileUnit>. Para generar código para un elemento **CodeCompileUnit** que contiene un gráfico CodeDOM, llame al método <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> del proveedor de código. Este método tiene un parámetro para <xref:System.IO.TextWriter> que se usa para generar el código fuente, por lo que a veces es necesario crear primero un elemento **TextWriter** en el que se pueda escribir. En el ejemplo siguiente se muestra la generación de código a partir de un elemento **CodeCompileUnit** y la escritura del código fuente generado en un archivo denominado HelloWorld.cs.  
  
 [!code-cpp[CodeDomExample#22](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#22)]
 [!code-csharp[CodeDomExample#22](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#22)]
 [!code-vb[CodeDomExample#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#22)]  
  
## <a name="using-a-codedom-code-provider-to-compile-assemblies"></a>Uso de un proveedor de código CodeDOM para compilar ensamblados  
 **Invocación de la compilación**  
  
 Para compilar un ensamblado mediante un proveedor CodeDom, se debe tener código fuente para compilar en un lenguaje para el que se tenga un compilador, o bien se debe disponer de un gráfico CodeDOM a partir del que se pueda generar ese código fuente que se va a compilar.  
  
 Si está compilando a partir de un gráfico CodeDOM, pase el elemento <xref:System.CodeDom.CodeCompileUnit> que contiene el gráfico al método <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A> del proveedor de código. Si tiene un archivo de código fuente en un lenguaje que el compilador entiende, pase el nombre del archivo que contiene el código fuente al método <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> del proveedor CodeDom. También puede pasar una cadena que contiene el código fuente en un lenguaje que el compilador entiende al método <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A> del proveedor CodeDom.  
  
 **Configuración de parámetros de compilación**  
  
 Todos los métodos de invocación de compilación estándar de un proveedor CodeDom tienen un parámetro de tipo <xref:System.CodeDom.Compiler.CompilerParameters> que indica las opciones que se van a usar para la compilación.  
  
 Puede especificar un nombre de archivo para el ensamblado de salida en la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.OutputAssembly%2A> de **CompilerParameters**. De lo contrario, se usará un nombre de archivo de salida predeterminado.  
  
 De forma predeterminada, se inicializa un nuevo elemento **CompilerParameters** con su propiedad <xref:System.CodeDom.Compiler.CompilerParameters.GenerateExecutable%2A> establecida en **false**. Si está compilando un programa ejecutable, debe establecer la propiedad **GenerateExecutable** en **true**. Cuando **GenerateExecutable** está establecida en **false**, el compilador genera una biblioteca de clases.  
  
 Si está compilando un ejecutable a partir de un gráfico CodeDOM, se debe definir un elemento <xref:System.CodeDom.CodeEntryPointMethod> en el gráfico. Si hay varios puntos de entrada de código, puede ser necesario establecer la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.MainClass%2A> de **CompilerParameters** en el nombre de la clase que define el punto de entrada que se va a usar.  
  
 Para incluir información de depuración en un archivo ejecutable generado, establezca la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.IncludeDebugInformation%2A> en **true**.  
  
 Si el proyecto hace referencia a algún ensamblado, debe especificar los nombres de ensamblado como elementos de una <xref:System.Collections.Specialized.StringCollection> como la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.ReferencedAssemblies%2A> de **CompilerParameters** que usa al invocar la compilación.  
  
 Puede compilar un ensamblado que se escribe en memoria en lugar de en disco si establece la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.GenerateInMemory%2A> en **true**. Cuando se genera un ensamblado en memoria, el código puede obtener una referencia al ensamblado generado a partir de la propiedad <xref:System.CodeDom.Compiler.CompilerResults.CompiledAssembly%2A> de <xref:System.CodeDom.Compiler.CompilerResults>. Si un ensamblado se escribe en disco, puede obtener la ruta de acceso al ensamblado generado a partir de la propiedad <xref:System.CodeDom.Compiler.CompilerResults.PathToAssembly%2A> de **CompilerResults**.  
  
 Para especificar una cadena de argumentos de línea de comandos personalizada que se usará al invocar al proceso de compilación, establezca la cadena en la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A>.  
  
 Si se necesita un token de seguridad de Win32 para invocar al proceso de compilación, especifique el token en la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.UserToken%2A>.  
  
 Para vincular un archivo de recursos de Win32 al ensamblado compilado, especifique el nombre del archivo de recursos de Win32 en la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.Win32Resource%2A>.  
  
 Para especificar un nivel de advertencia en el que detener la compilación, establezca la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.WarningLevel%2A> en un entero que represente el nivel de advertencia en el que detener la compilación. También puede establecer la propiedad <xref:System.CodeDom.Compiler.CompilerParameters.TreatWarningsAsErrors%2A> en **true** para que se detenga la compilación si se producen advertencias.  
  
 En el ejemplo de código siguiente se muestra cómo compilar un archivo de origen con un proveedor CodeDom derivado de la clase <xref:System.CodeDom.Compiler.CodeDomProvider>.  
  
 [!code-cpp[CodeDomExample#23](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#23)]
 [!code-csharp[CodeDomExample#23](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#23)]
 [!code-vb[CodeDomExample#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#23)]  
  
## <a name="languages-with-initial-support"></a>Lenguajes con compatibilidad inicial  
 .NET Framework proporciona compiladores y generadores de código para los lenguajes siguientes: C#, Visual Basic, C++ y JScript. La compatibilidad de CodeDOM se puede extender a otros lenguajes si se implementan generadores y compiladores de código específicos del lenguaje.  
  
## <a name="see-also"></a>Vea también

- <xref:System.CodeDom>
- <xref:System.CodeDom.Compiler>
- [Generación y compilación dinámicas de código fuente](dynamic-source-code-generation-and-compilation.md)
- [Referencia rápida de CodeDOM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100))
