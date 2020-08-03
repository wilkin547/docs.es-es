---
title: Procedimiento para crear un clase mediante CodeDOM
description: Vea un ejemplo detallado en el que se explica cómo crear una clase mediante Code Document Object Model (CodeDOM).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Code Document Object Model, graphs
- Code Document Object Model, creating classes
- graphing with CodeDOM
- CodeDOM, creating classes
- CodeDOM, graphs
ms.assetid: 0ceb70fe-36e1-49bb-922b-e9f615c20a14
ms.openlocfilehash: 3d7151d384402dba6fbb5da8fe54621346251f7b
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865312"
---
# <a name="how-to-create-a-class-using-codedom"></a>Procedimiento para crear un clase mediante CodeDOM
En los procedimientos siguientes se muestra cómo crear y compilar un gráfico CodeDOM que genera una clase que contiene dos campos, tres propiedades, un método, un constructor y un punto de entrada.  
  
1. Cree una aplicación de consola que usará el código CodeDOM para generar el código fuente para una clase.  
  
     En este ejemplo, la clase generadora se denomina `Sample`, mientras que el código generado es una clase denominada `CodeDOMCreatedClass` en un archivo llamado SampleCode.  
  
2. En la clase generadora, inicialice el gráfico CodeDOM y use los métodos CodeDOM para definir los miembros, el constructor y el punto de entrada (método `Main`) de la clase generada.  
  
     En este ejemplo, la clase generada tiene dos campos, tres propiedades, un constructor, un método y el método `Main`.  
  
3. En la clase generadora, cree un proveedor de código específico del lenguaje y llame a su método <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> para generar el código a partir del gráfico.  
  
4. Compile y ejecute la aplicación para generar el código.  
  
     En este ejemplo, el código generado se encuentra en un archivo llamado SampleCode. Compile y ejecute este código para ver la salida de ejemplo.  
  
### <a name="to-create-the-application-that-will-execute-the-codedom-code"></a>Para crear la aplicación que ejecutará el código CodeDOM  
  
- Cree una clase de aplicación de consola que contenga el código CodeDOM. Defina los campos globales que se van a usar en la clase para hacer referencia al ensamblado (<xref:System.CodeDom.CodeCompileUnit>) y a la clase (<xref:System.CodeDom.CodeTypeDeclaration>), especifique el nombre del archivo de código fuente generado y declare el método `Main`.  
  
     [!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]
     [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]  
  
### <a name="to-initialize-the-codedom-graph"></a>Para inicializar el gráfico CodeDOM  
  
- En el constructor de la clase de aplicación de consola, inicialice el ensamblado y la clase, y agregue las declaraciones adecuadas al gráfico CodeDOM.  
  
     [!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]
     [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]  
  
### <a name="to-add-members-to-the-codedom-graph"></a>Para agregar miembros al gráfico CodeDOM  
  
- Agregue campos al gráfico CodeDOM agregando objetos <xref:System.CodeDom.CodeMemberField> a la propiedad <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> de la clase.  
  
     [!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]
     [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]  
  
- Agregue propiedades al gráfico CodeDOM agregando objetos <xref:System.CodeDom.CodeMemberProperty> a la propiedad <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> de la clase.  
  
     [!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]
     [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]  
  
- Agregue un método al gráfico CodeDOM agregando un objeto <xref:System.CodeDom.CodeMemberMethod> a la propiedad <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> de la clase.  
  
     [!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]
     [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]  
  
- Agregue un constructor al gráfico CodeDOM agregando un objeto <xref:System.CodeDom.CodeConstructor> a la propiedad <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> de la clase.  
  
     [!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]
     [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]  
  
- Agregue un punto de entrada al gráfico CodeDOM agregando un objeto <xref:System.CodeDom.CodeEntryPointMethod> a la propiedad <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> de la clase.  
  
     [!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]
     [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]  
  
### <a name="to-generate-the-code-from-the-codedom-graph"></a>Para generar el código a partir del gráfico CodeDOM  
  
- Genere el código fuente a partir del gráfico CodeDOM llamando al método <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>.  
  
     [!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]
     [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]  
  
### <a name="to-create-the-graph-and-generate-the-code"></a>Para crear el gráfico y generar el código  
  
1. Agregue los métodos creados en los pasos anteriores al método `Main` definido en el primer paso.  
  
     [!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]
     [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]  
  
2. Compile y ejecute la clase generadora.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo de código se muestra el código de los pasos anteriores.  
  
 [!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)]
 [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]  
  
 Cuando se compila y se ejecuta el ejemplo anterior, genera el siguiente código fuente.  
  
 [!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)]
 [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]  
  
 El código fuente generado produce el siguiente resultado cuando se compila y ejecuta.  
  
```output
The object:  
 width = 5.3,  
 height = 6.9,  
 area = 36.57  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- En este ejemplo de código, el permiso `FullTrust` debe estar establecido para que se ejecute correctamente.  
  
## <a name="see-also"></a>Vea también

- [Usar CodeDOM](using-the-codedom.md)
- [Generar y compilar código fuente a partir de un gráfico CodeDOM](generating-and-compiling-source-code-from-a-codedom-graph.md)
