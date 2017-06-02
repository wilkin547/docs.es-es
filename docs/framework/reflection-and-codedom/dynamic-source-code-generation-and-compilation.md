---
title: "Dynamic Source Code Generation and Compilation | Microsoft Docs"
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
  - "Code Document Object Model"
  - "System.CodeDom namespace"
  - "language-independent source code modeling"
  - "CodeDOM"
  - "multiple languages supported by CodeDOM"
  - "source code in multiple languages"
  - "languages, multiple language support by CodeDOM"
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Dynamic Source Code Generation and Compilation
.NET Framework dispone de un mecanismo denominado CodeDOM \(Code Document Object Model\) que permite que los programadores que emiten código fuente generen el código fuente en varios lenguajes de programación en tiempo de ejecución, basándose en un único modelo que representa el código que se va a generar.  
  
 Para representar el código fuente, los elementos de CodeDOM se vinculan entre sí para formar una estructura de datos conocida como gráfico CodeDOM, que modela la estructura de parte del código fuente.  
  
 El espacio de nombres `System.CodeDom` define los tipos que pueden representar la estructura lógica del código fuente, independientemente de un lenguaje de programación específico.  El espacio de nombres `System.CodeDom.Compiler` define los tipos para generar código fuente a partir de gráficos CodeDOM y para administrar la compilación del código fuente en los lenguajes admitidos.  Los proveedores de compiladores o los programadores pueden extender el conjunto de lenguajes admitidos.  
  
 El modelo de código fuente independiente del lenguaje puede ser valioso cuando un programa necesita generar código fuente para un modelo de programa en varios lenguajes o para un lenguaje de destino incierto.  Por ejemplo, algunos diseñadores utilizan el CodeDOM como una interfaz de abstracción del lenguaje para generar código fuente en el lenguaje de programación correcto, si dicho lenguaje es compatible con CodeDOM.  
  
 .NET Framework dispone de generadores de código y compiladores de código para [C\#](frlrfMicrosoftCSharpCSharpCodeProviderClassTopic), [JScript](frlrfMicrosoftJScriptJScriptCodeProviderClassTopic) y [Visual Basic](frlrfMicrosoftVisualBasicVBCodeProviderClassTopic).  
  
## En esta sección  
 [Usar CodeDOM](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)  
 Describe su uso más habitual y muestra cómo compilar un gráfico de objetos simple utilizando CodeDOM.  
  
 [Generar código fuente y compilar un programa a partir de un gráfico CodeDOM](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)  
 Describe cómo generar código fuente y compilar el código generado con un compilador externo utilizando las clases definidas en el espacio de nombres `System.CodeDom.Compiler`.  
  
 [How to: Create an XML Documentation File Using CodeDOM](../../../docs/framework/reflection-and-codedom/how-to-create-an-xml-documentation-file-using-codedom.md)  
 Describe cómo utilizar CodeDOM para generar código con comentarios de documentación XML y compilar el código generado para que cree la documentación XML resultante.  
  
 [How to: Create a Class Using CodeDOM](../../../docs/framework/reflection-and-codedom/how-to-create-a-class-using-codedom.md)  
 Describe cómo utilizar CodeDOM para generar una clase que contenga campos, propiedades, un método, un constructor y un punto de entrada.  
  
## Referencia  
 <xref:System.CodeDom>  
 Define los elementos que representan los elementos de código de los lenguajes de programación orientados a Common Language Runtime.  
  
 <xref:System.CodeDom.Compiler>  
 Define interfaces para generar y compilar código en tiempo de ejecución.  
  
## Secciones relacionadas  
 [Referencia rápida de CodeDOM](http://msdn.microsoft.com/es-es/c77b8bfd-0a32-4e36-b59a-4f687f32c524)  
 Permite a los programadores encontrar los elementos de CodeDOM que representan elementos del código fuente.