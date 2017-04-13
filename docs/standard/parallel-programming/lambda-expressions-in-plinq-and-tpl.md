---
title: "Lambda Expressions in PLINQ and TPL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Func delegate, creating with lambda expression"
  - "Action delegate, creating with lambda expression"
  - "lambda expressions, with Action and Func"
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Lambda Expressions in PLINQ and TPL
La biblioteca TPL \(Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas\) contiene muchos métodos que toman una de las familias de delegados <xref:System.Func%601?displayProperty=fullName> o <xref:System.Action?displayProperty=fullName> como parámetros de entrada.  Estos delegados se usan para pasar la lógica del programa personalizado al bucle, tarea o consulta paralelo.  Los ejemplos de código de TPL, así como PLINQ, usan expresiones lambda para crear instancias de los delegados como bloques de código alineado.  En este tema se proporciona una breve introducción a Func y Action, y se muestra cómo usar las expresiones lambda en la biblioteca TPL y PLINQ.  
  
 **Nota** Para obtener más información sobre los delegados en general, vea [Delegados](../Topic/Delegates%20\(C%23%20Programming%20Guide\).md) y [Delegados](../Topic/Delegates%20\(Visual%20Basic\).md).  Para obtener más información sobre las expresiones lambda en C\# y [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], vea [Expresiones lambda](../Topic/Lambda%20Expressions%20\(C%23%20Programming%20Guide\).md) y [Expresiones lambda](../Topic/Lambda%20Expressions%20\(Visual%20Basic\).md).  
  
## Delegado Func  
 Un delegado `Func` encapsula un método que devuelve un valor.  En una signatura de Func, el último parámetro de tipo, o el situado en el extremo derecho, siempre especifica el tipo de valor devuelto.  Una causa común de los errores del compilador es el intento de pasar dos parámetros de entrada a <xref:System.Func%602?displayProperty=fullName>; de hecho, este tipo toma un único parámetro de entrada.  La biblioteca de clases de .NET Framework define 17 versiones de `Func`: <xref:System.Func%601?displayProperty=fullName>, <xref:System.Func%602?displayProperty=fullName>, <xref:System.Func%603?displayProperty=fullName>, y así sucesivamente hasta <xref:System.Func%6017?displayProperty=fullName>.  
  
## Delegado Action  
 Un delegado <xref:System.Action?displayProperty=fullName> encapsula un método \(Sub en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) que no devuelve ningún valor o que devuelve [void](../Topic/void%20\(C%23%20Reference\).md).  En una signatura de Action, los parámetros de tipo solamente representan parámetros de entrada.  Al igual que sucede con Func, la biblioteca de clases de .NET Framework define 17 versiones de Action, desde una versión que no tiene ningún parámetro de tipo hasta una versión con 16 parámetros de tipo.  
  
## Ejemplo  
 En el ejemplo siguiente del método <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=fullName> se muestra cómo expresar los delegados Func y Action mediante expresiones lambda.  
  
 [!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
 [!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]  
  
## Vea también  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)