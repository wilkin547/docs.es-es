---
title: "Cómo: Crear un clase utilizando CodeDOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d92af3e2a04588e3942dd6c8c0625c607e08f123
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-class-using-codedom"></a><span data-ttu-id="e4c64-102">Cómo: Crear un clase utilizando CodeDOM</span><span class="sxs-lookup"><span data-stu-id="e4c64-102">How to: Create a Class Using CodeDOM</span></span>
<span data-ttu-id="e4c64-103">En los procedimientos siguientes se muestra cómo crear y compilar un gráfico CodeDOM que genera una clase que contiene dos campos, tres propiedades, un método, un constructor y un punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="e4c64-103">The following procedures illustrate how to create and compile a CodeDOM graph that generates a class containing two fields, three properties, a method, a constructor, and an entry point.</span></span>  
  
1.  <span data-ttu-id="e4c64-104">Cree una aplicación de consola que usará el código CodeDOM para generar el código fuente para una clase.</span><span class="sxs-lookup"><span data-stu-id="e4c64-104">Create a console application that will use CodeDOM code to generate the source code for a class.</span></span>  
  
     <span data-ttu-id="e4c64-105">En este ejemplo, la clase generadora se denomina `Sample`, mientras que el código generado es una clase denominada `CodeDOMCreatedClass` en un archivo llamado SampleCode.</span><span class="sxs-lookup"><span data-stu-id="e4c64-105">In this example, the generating class is named `Sample`, and the generated code is a class named `CodeDOMCreatedClass` in a file named SampleCode.</span></span>  
  
2.  <span data-ttu-id="e4c64-106">En la clase generadora, inicialice el gráfico CodeDOM y use los métodos CodeDOM para definir los miembros, el constructor y el punto de entrada (método `Main`) de la clase generada.</span><span class="sxs-lookup"><span data-stu-id="e4c64-106">In the generating class, initialize the CodeDOM graph and use CodeDOM methods to define the members, constructor, and entry point (`Main` method) of the generated class.</span></span>  
  
     <span data-ttu-id="e4c64-107">En este ejemplo, la clase generada tiene dos campos, tres propiedades, un constructor, un método y el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="e4c64-107">In this example, the generated class has two fields, three properties, a constructor, a method, and a `Main` method.</span></span>  
  
3.  <span data-ttu-id="e4c64-108">En la clase generadora, cree un proveedor de código específico del lenguaje y llame a su método <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> para generar el código a partir del gráfico.</span><span class="sxs-lookup"><span data-stu-id="e4c64-108">In the generating class, create a language-specific code provider and call its <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code from the graph.</span></span>  
  
4.  <span data-ttu-id="e4c64-109">Compile y ejecute la aplicación para generar el código.</span><span class="sxs-lookup"><span data-stu-id="e4c64-109">Compile and execute the application to generate the code.</span></span>  
  
     <span data-ttu-id="e4c64-110">En este ejemplo, el código generado se encuentra en un archivo llamado SampleCode.</span><span class="sxs-lookup"><span data-stu-id="e4c64-110">In this example, the generated code is in a file named SampleCode.</span></span> <span data-ttu-id="e4c64-111">Compile y ejecute este código para ver la salida de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e4c64-111">Compile and execute that code to see the sample output.</span></span>  
  
### <a name="to-create-the-application-that-will-execute-the-codedom-code"></a><span data-ttu-id="e4c64-112">Para crear la aplicación que ejecutará el código CodeDOM</span><span class="sxs-lookup"><span data-stu-id="e4c64-112">To create the application that will execute the CodeDOM code</span></span>  
  
-   <span data-ttu-id="e4c64-113">Cree una clase de aplicación de consola que contenga el código CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="e4c64-113">Create a console application class to contain the CodeDOM code.</span></span> <span data-ttu-id="e4c64-114">Defina los campos globales que se van a usar en la clase para hacer referencia al ensamblado (<xref:System.CodeDom.CodeCompileUnit>) y a la clase (<xref:System.CodeDom.CodeTypeDeclaration>), especifique el nombre del archivo de código fuente generado y declare el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="e4c64-114">Define the global fields that are to be used in the class to reference the assembly (<xref:System.CodeDom.CodeCompileUnit>) and class (<xref:System.CodeDom.CodeTypeDeclaration>), specify the name of the generated source file, and declare the `Main` method.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]
     [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]  
  
### <a name="to-initialize-the-codedom-graph"></a><span data-ttu-id="e4c64-115">Para inicializar el gráfico CodeDOM</span><span class="sxs-lookup"><span data-stu-id="e4c64-115">To initialize the CodeDOM graph</span></span>  
  
-   <span data-ttu-id="e4c64-116">En el constructor de la clase de aplicación de consola, inicialice el ensamblado y la clase, y agregue las declaraciones adecuadas al gráfico CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="e4c64-116">In the constructor for the console application class, initialize the assembly and class, and add the appropriate declarations to the CodeDOM graph.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]
     [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]  
  
### <a name="to-add-members-to-the-codedom-graph"></a><span data-ttu-id="e4c64-117">Para agregar miembros al gráfico CodeDOM</span><span class="sxs-lookup"><span data-stu-id="e4c64-117">To add members to the CodeDOM graph</span></span>  
  
-   <span data-ttu-id="e4c64-118">Agregue campos al gráfico CodeDOM agregando objetos <xref:System.CodeDom.CodeMemberField> a la propiedad <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> de la clase.</span><span class="sxs-lookup"><span data-stu-id="e4c64-118">Add fields to the CodeDOM graph by adding <xref:System.CodeDom.CodeMemberField> objects to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]
     [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]  
  
-   <span data-ttu-id="e4c64-119">Agregue propiedades al gráfico CodeDOM agregando objetos <xref:System.CodeDom.CodeMemberProperty> a la propiedad <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> de la clase.</span><span class="sxs-lookup"><span data-stu-id="e4c64-119">Add properties to the CodeDOM graph by adding <xref:System.CodeDom.CodeMemberProperty> objects to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]
     [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]  
  
-   <span data-ttu-id="e4c64-120">Agregue un método al gráfico CodeDOM agregando un objeto <xref:System.CodeDom.CodeMemberMethod> a la propiedad <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> de la clase.</span><span class="sxs-lookup"><span data-stu-id="e4c64-120">Add a method to the CodeDOM graph by adding a <xref:System.CodeDom.CodeMemberMethod> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]
     [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]  
  
-   <span data-ttu-id="e4c64-121">Agregue un constructor al gráfico CodeDOM agregando un objeto <xref:System.CodeDom.CodeConstructor> a la propiedad <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> de la clase.</span><span class="sxs-lookup"><span data-stu-id="e4c64-121">Add a constructor to the CodeDOM graph by adding a <xref:System.CodeDom.CodeConstructor> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]
     [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]  
  
-   <span data-ttu-id="e4c64-122">Agregue un punto de entrada al gráfico CodeDOM agregando un objeto <xref:System.CodeDom.CodeEntryPointMethod> a la propiedad <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> de la clase.</span><span class="sxs-lookup"><span data-stu-id="e4c64-122">Add an entry point to the CodeDOM graph by adding a <xref:System.CodeDom.CodeEntryPointMethod> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]
     [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]  
  
### <a name="to-generate-the-code-from-the-codedom-graph"></a><span data-ttu-id="e4c64-123">Para generar el código a partir del gráfico CodeDOM</span><span class="sxs-lookup"><span data-stu-id="e4c64-123">To generate the code from the CodeDOM graph</span></span>  
  
-   <span data-ttu-id="e4c64-124">Genere el código fuente a partir del gráfico CodeDOM llamando al método <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4c64-124">Generate source code from the CodeDOM graph by calling the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]
     [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]  
  
### <a name="to-create-the-graph-and-generate-the-code"></a><span data-ttu-id="e4c64-125">Para crear el gráfico y generar el código</span><span class="sxs-lookup"><span data-stu-id="e4c64-125">To create the graph and generate the code</span></span>  
  
1.  <span data-ttu-id="e4c64-126">Agregue los métodos creados en los pasos anteriores al método `Main` definido en el primer paso.</span><span class="sxs-lookup"><span data-stu-id="e4c64-126">Add the methods created in the preceding steps to the `Main` method defined in the first step.</span></span>  
  
     [!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]
     [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]  
  
2.  <span data-ttu-id="e4c64-127">Compile y ejecute la clase generadora.</span><span class="sxs-lookup"><span data-stu-id="e4c64-127">Compile and execute the generating class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4c64-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4c64-128">Example</span></span>  
 <span data-ttu-id="e4c64-129">En el siguiente ejemplo de código se muestra el código de los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="e4c64-129">The following code example shows the code from the preceding steps.</span></span>  
  
 [!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)]
 [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]  
  
 <span data-ttu-id="e4c64-130">Cuando se compila y se ejecuta el ejemplo anterior, genera el siguiente código fuente.</span><span class="sxs-lookup"><span data-stu-id="e4c64-130">When the preceding example is compiled and executed, it produces the following source code.</span></span>  
  
 [!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)]
 [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]  
  
 <span data-ttu-id="e4c64-131">El código fuente generado produce el siguiente resultado cuando se compila y ejecuta.</span><span class="sxs-lookup"><span data-stu-id="e4c64-131">The generated source code produces the following output when compiled and executed.</span></span>  
  
```  
The object:  
 width = 5.3,  
 height = 6.9,  
 area = 36.57  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e4c64-132">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e4c64-132">Compiling the Code</span></span>  
  
-   <span data-ttu-id="e4c64-133">En este ejemplo de código, el permiso `FullTrust` debe estar establecido para que se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="e4c64-133">This code example requires the `FullTrust` permission set to execute successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4c64-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4c64-134">See Also</span></span>  
 [<span data-ttu-id="e4c64-135">Usar CodeDOM</span><span class="sxs-lookup"><span data-stu-id="e4c64-135">Using the CodeDOM</span></span>](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)  
 [<span data-ttu-id="e4c64-136">Generar y compilar código fuente a partir de un gráfico CodeDOM</span><span class="sxs-lookup"><span data-stu-id="e4c64-136">Generating and Compiling Source Code from a CodeDOM Graph</span></span>](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)
