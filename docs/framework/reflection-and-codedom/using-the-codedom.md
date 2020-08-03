---
title: Usar CodeDOM
description: Use Code Document Object Model (CodeDOM), que proporciona tipos que representan muchos tipos comunes de elementos de código fuente, para ensamblar un gráfico de objetos.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- code compilers
- Code Document Object Model
- Code Document Object Model, graphs
- types, CodeDOM
- namespaces [.NET Framework], CodeDOM
- templated code generation
- dynamically representing source code
- source code models
- CodeDOM
- graphing with CodeDOM
- dynamic compilation
- code generators
- CodeDOM, graphs
ms.assetid: 0444ddf3-c3f6-44ed-a999-f710d9c3e0cf
ms.openlocfilehash: 476d8c18f386f889855c664147b1ee20995dc6f9
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865221"
---
# <a name="using-the-codedom"></a>Usar CodeDOM
CodeDOM proporciona tipos que representan muchos tipos comunes de elementos de código fuente. Se puede diseñar un programa que compile un modelo de código fuente utilizando los elementos de CodeDOM para ensamblar un gráfico de objetos. Este gráfico de objetos se puede representar como código fuente utilizando un generador de código de CodeDOM para un lenguaje de programación compatible. CodeDOM también se puede utilizar para compilar código fuente en un ensamblado binario.  
  
 Algunos usos habituales de CodeDOM son:  
  
- Generación de código mediante plantillas: generación de código para ASP.NET, proxies de clientes de servicios Web XML, asistentes para código, diseñadores y otros mecanismos de emisión de código.  
  
- Compilación dinámica: compatibilidad para compilación de código en uno o varios lenguajes.  
  
## <a name="building-a-codedom-graph"></a>Compilar un gráfico CodeDOM  
 El espacio de nombres <xref:System.CodeDom> proporciona clases para representar la estructura lógica del código fuente, independientemente de la sintaxis del lenguaje.  
  
### <a name="the-structure-of-a-codedom-graph"></a>La estructura de un gráfico CodeDOM  
 La estructura de un gráfico CodeDOM es similar a un árbol de contenedores. El contenedor raíz o el contenedor superior de cada gráfico CodeDOM compilable es una unidad <xref:System.CodeDom.CodeCompileUnit>. Todos y cada uno de los elementos del modelo de código fuente deben estar vinculados en el gráfico mediante una propiedad de un objeto <xref:System.CodeDom.CodeObject> del gráfico.  
  
### <a name="building-a-source-code-model-for-a-sample-hello-world-program"></a>Compilar un modelo de código fuente para el programa de ejemplo Hola a todos  
 En el siguiente tutorial se muestra un ejemplo de cómo compilar un gráfico de objetos CodeDOM que representa el código de una aplicación Hola a todos sencilla. Para obtener el código fuente completo de este código de ejemplo, vea el tema <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.  
  
#### <a name="creating-a-compile-unit"></a>Crear una unidad de compilación  
 CodeDOM define un objeto denominado <xref:System.CodeDom.CodeCompileUnit>, que puede hacer referencia a un gráfico de objetos CodeDOM que modela el código fuente que se va a compilar. Un objeto **CodeCompileUnit** dispone de propiedades para almacenar referencias a atributos, espacios de nombres y ensamblados.  
  
 Los proveedores CodeDom que derivan de la clase <xref:System.CodeDom.Compiler.CodeDomProvider> contienen métodos que procesan el gráfico de objetos a los que hace referencia **CodeCompileUnit**.  
  
 Para crear un gráfico de objetos para una aplicación sencilla, debe ensamblar el modelo de código fuente y hacer referencia a él desde **CodeCompileUnit**.  
  
 Se puede crear una nueva unidad de compilación con la sintaxis que muestra este ejemplo:  
  
 [!code-cpp[CodeDomExample#12](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#12)]
 [!code-csharp[CodeDomExample#12](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#12)]
 [!code-vb[CodeDomExample#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#12)]  
  
 <xref:System.CodeDom.CodeSnippetCompileUnit> puede contener una sección de código fuente que ya está en el lenguaje de destino pero que no se puede representar en otro lenguaje.  
  
#### <a name="defining-a-namespace"></a>Definir un espacio de nombres  
 Para definir un espacio de nombres, cree un objeto <xref:System.CodeDom.CodeNamespace> y asígnele un nombre con el constructor correspondiente o mediante el establecimiento de su propiedad **Name**.  
  
 [!code-cpp[CodeDomExample#13](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#13)]
 [!code-csharp[CodeDomExample#13](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#13)]
 [!code-vb[CodeDomExample#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#13)]  
  
#### <a name="importing-a-namespace"></a>Importar un espacio de nombres  
 Para agregar una directiva de importación de espacios de nombres al espacio de nombres, agregue una importación <xref:System.CodeDom.CodeNamespaceImport> que indique el espacio de nombres que se va a importar a la colección **CodeNamespace.Imports**.  
  
 En el siguiente código, se agrega una importación para el espacio de nombres **System** a la colección **Imports** de un espacio de nombres **CodeNamespace** denominado `samples`:  
  
 [!code-cpp[CodeDomExample#14](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#14)]
 [!code-csharp[CodeDomExample#14](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#14)]
 [!code-vb[CodeDomExample#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#14)]  
  
#### <a name="linking-code-elements-into-the-object-graph"></a>Vincular elementos de código al gráfico de objetos  
 Todos los elementos de código que forman un gráfico CodeDOM deben estar vinculados a <xref:System.CodeDom.CodeCompileUnit>, que es el elemento raíz del árbol, mediante una serie de referencias entre elementos a los que se hace directamente referencia desde las propiedades del objeto raíz del gráfico. Establezca un objeto en una propiedad de un objeto de contenedor para establecer una referencia desde el objeto de contenedor.  
  
 La instrucción siguiente agrega el **CodeNamespace** `samples` a la propiedad de colección **Namespaces** del objeto raíz **CodeCompileUnit**.  
  
 [!code-cpp[CodeDomExample#15](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#15)]
 [!code-csharp[CodeDomExample#15](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#15)]
 [!code-vb[CodeDomExample#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#15)]  
  
#### <a name="defining-a-type"></a>Definir un tipo  
 Para declarar una clase, estructura, interfaz o enumeración utilizando CodeDOM, cree un nuevo objeto <xref:System.CodeDom.CodeTypeDeclaration> y asígnele un nombre. En el siguiente ejemplo se muestra cómo hacerlo mediante una sobrecarga de constructor para establecer la propiedad **Name**:  
  
 [!code-cpp[CodeDomExample#16](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#16)]
 [!code-csharp[CodeDomExample#16](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#16)]
 [!code-vb[CodeDomExample#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#16)]  
  
 Para agregar un tipo a un espacio de nombres, agregue una declaración <xref:System.CodeDom.CodeTypeDeclaration> que represente el tipo que se va a agregar al espacio de nombres de la colección **Types** de un espacio de nombres **CodeNamespace**.  
  
 En el siguiente ejemplo se muestra cómo agregar una clase denominada `class1` a un espacio de nombres **CodeNamespace** denominado `samples`:  
  
 [!code-cpp[CodeDomExample#17](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#17)]
 [!code-csharp[CodeDomExample#17](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#17)]
 [!code-vb[CodeDomExample#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#17)]  
  
#### <a name="adding-class-members-to-a-class"></a>Agregar miembros de clase a una clase  
 El espacio de nombres <xref:System.CodeDom> dispone de diferentes elementos que se pueden utilizar para representar miembros de clase. Todos los miembros de clase pueden agregarse a la colección **Members** de una declaración <xref:System.CodeDom.CodeTypeDeclaration>.  
  
#### <a name="defining-a-code-entry-point-method-for-an-executable"></a>Definir un método de punto de entrada de código para un archivo ejecutable  
 Si desea compilar el código de un programa ejecutable, es necesario indicar el punto de entrada de un programa creando un objeto <xref:System.CodeDom.CodeEntryPointMethod> que represente el método en el que debe comenzar la ejecución del programa.  
  
 En el siguiente ejemplo se muestra cómo definir un método de punto de entrada que contiene una expresión <xref:System.CodeDom.CodeMethodInvokeExpression> que llama a **System.Console.WriteLine** para imprimir "Hello World!":  
  
 [!code-cpp[CodeDomExample#18](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#18)]
 [!code-csharp[CodeDomExample#18](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#18)]
 [!code-vb[CodeDomExample#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#18)]  
  
 La siguiente instrucción agrega el método de punto de entrada denominado `Start` a la colección **Members** de `class1`:  
  
 [!code-cpp[CodeDomExample#19](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#19)]
 [!code-csharp[CodeDomExample#19](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#19)]
 [!code-vb[CodeDomExample#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#19)]  
  
 Ahora, la unidad <xref:System.CodeDom.CodeCompileUnit> denominada `compileUnit` contiene el gráfico CodeDOM para un programa Hello World sencillo. Para obtener información sobre la forma de generar y compilar código desde un gráfico CodeDOM, vea [Generar código fuente y compilar un programa a partir de un gráfico CodeDOM](generating-and-compiling-source-code-from-a-codedom-graph.md).  
  
### <a name="more-information-on-building-a-codedom-graph"></a>Más información sobre la forma de compilar un gráfico CodeDOM.  
 CodeDOM admite muchos de los tipos comunes de elementos de código que se encuentran en los lenguajes de programación compatibles con Common Language Runtime. CodeDOM no fue diseñado para disponer de elementos que representen todas las características posibles de un lenguaje de programación. El código que no se puede representar fácilmente con elementos CodeDOM se puede encapsular en un <xref:System.CodeDom.CodeSnippetExpression>, <xref:System.CodeDom.CodeSnippetStatement>, <xref:System.CodeDom.CodeSnippetTypeMember> o <xref:System.CodeDom.CodeSnippetCompileUnit>. No obstante, los miniprogramas no pueden traducirse automáticamente a otros lenguajes por medio de CodeDOM.  
  
 Para obtener documentación de cada uno de los tipos CodeDOM, consulte la documentación de referencia del espacio de nombres <xref:System.CodeDom>.  
  
 Para ver un gráfico que localice rápidamente el elemento de CodeDOM que representa un tipo específico de elemento de código, vea [Referencia rápida de CodeDOM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)).
