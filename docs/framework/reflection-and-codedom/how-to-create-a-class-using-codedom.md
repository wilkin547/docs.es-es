---
title: "How to: Create a Class Using CodeDOM | Microsoft Docs"
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
  - "Code Document Object Model, graphs"
  - "Code Document Object Model, creating classes"
  - "graphing with CodeDOM"
  - "CodeDOM, creating classes"
  - "CodeDOM, graphs"
ms.assetid: 0ceb70fe-36e1-49bb-922b-e9f615c20a14
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Create a Class Using CodeDOM
Los procedimientos siguientes muestran cómo crear y compilar un gráfico CodeDOM que genera una clase que contiene dos campos, tres propiedades, un método, un constructor y un punto de entrada.  
  
1.  Cree una aplicación de consola que vaya a utilizar el código CodeDOM para generar el código fuente para una clase.  
  
     En este ejemplo, la clase generadora se denomina `Sample` y el código generado es una clase denominada `CodeDOMCreatedClass` en un archivo llamado SampleCode.  
  
2.  En la clase generadora, inicialice el gráfico CodeDOM y utilice los métodos CodeDOM para definir los miembros, el constructor y el punto de entrada \(método `Main`\) de la clase generada.  
  
     En este ejemplo, la clase generada tiene dos campos, tres propiedades, un constructor, un método y un método `Main`.  
  
3.  En la clase generadora, cree un proveedor de código específico del lenguaje y llame a su método <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> para generar el código del gráfico.  
  
4.  Compile y ejecute la aplicación para generar el código.  
  
     En este ejemplo, el código generado está en un archivo denominado SampleCode.  Compile y ejecute este código para ver el resultado de ejemplo.  
  
### Para crear la aplicación que va a ejecutar el código CodeDOM  
  
-   Cree una clase de aplicación de consola que va a contener el código CodeDOM.  Defina los campos globales que se van a utilizar en la clase para hacer referencia al ensamblado \(<xref:System.CodeDom.CodeCompileUnit>\) y a la clase \(<xref:System.CodeDom.CodeTypeDeclaration>\), especifique el nombre del archivo de código fuente generado y declare el método `Main`.  
  
     [!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]
     [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]  
  
### Para inicializar el gráfico CodeDOM  
  
-   En el constructor para la clase de aplicación de consola, inicialice el ensamblado y la clase, y agregue las declaraciones adecuadas al gráfico CodeDOM.  
  
     [!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]
     [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]  
  
### Para agregar miembros al gráfico CodeDOM  
  
-   Agregue campos al gráfico CodeDOM agregando objetos <xref:System.CodeDom.CodeMemberField> a la propiedad <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> de la clase.  
  
     [!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]
     [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]  
  
-   Agregue propiedades al gráfico CodeDOM agregando objetos <xref:System.CodeDom.CodeMemberProperty> a la propiedad <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> de la clase.  
  
     [!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]
     [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]  
  
-   Agregue un método al gráfico CodeDOM agregando un objeto <xref:System.CodeDom.CodeMemberMethod> a la propiedad <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> de la clase.  
  
     [!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]
     [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]  
  
-   Agregue un constructor al gráfico CodeDOM agregando un objeto <xref:System.CodeDom.CodeConstructor> a la propiedad <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> de la clase.  
  
     [!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]
     [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]  
  
-   Agregue un punto de entrada al gráfico CodeDOM agregando un objeto <xref:System.CodeDom.CodeEntryPointMethod> a la propiedad <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> de la clase.  
  
     [!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]
     [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]  
  
### Para generar el código del gráfico CodeDOM  
  
-   Genere el código fuente del gráfico CodeDOM llamando al método <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>.  
  
     [!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]
     [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]  
  
### Para crear el gráfico y generar el código  
  
1.  Agregue los métodos creados en los pasos anteriores al método `Main` definido en el primer paso.  
  
     [!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]
     [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]  
  
2.  Compile y ejecute la clase generadora.  
  
## Ejemplo  
 El ejemplo de código siguiente muestra el código de los pasos anteriores.  
  
 [!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)]
 [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]  
  
 Cuando se compila y ejecuta el ejemplo anterior, se genera el código fuente siguiente.  
  
 [!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)]
 [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]  
  
 El código fuente generado produce el resultado siguiente cuando se compila y ejecuta.  
  
```  
The object:  
 width = 5.3,  
 height = 6.9,  
 area = 36.57  
```  
  
## Compilar el código  
  
-   Este ejemplo de código exige que el conjunto de permisos `FullTrust` se ejecute correctamente.  
  
## Vea también  
 [Using the CodeDOM](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)   
 [Generating and Compiling Source Code from a CodeDOM Graph](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)