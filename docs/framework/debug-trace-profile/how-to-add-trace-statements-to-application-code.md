---
title: "How to: Add Trace Statements to Application Code | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "tracing [.NET Framework], conditional writes based on switches"
  - "trace statements"
  - "WriteLineIf method"
  - "tracing [.NET Framework], adding trace statements"
  - "Assert method, tracing code"
  - "trace switches, conditional writes based on switches"
  - "WriteIf method"
ms.assetid: f3a93fa7-1717-467d-aaff-393e5c9828b4
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# How to: Add Trace Statements to Application Code
Los métodos que se usan con mayor frecuencia para traza son los métodos para escribir los resultados para agentes de escucha: **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert** y **Fail**.  Estos métodos se pueden dividir en dos categorías: **Write**, **WriteLine** y **Fail** emiten resultados de forma incondicional, mientras que **WriteIf**, **WriteLineIf** y **Assert** prueban una condición booleana y escriben o no escriben en función del valor de la condición.  **WriteIf** y **WriteLineIf** emiten resultados si la condición es `true` y **Assert** emite resultados si la condición es `false`.  
  
 Al diseñar la estrategia de depuración y traza, debe pensar cómo desea presentar los resultados.  Varias instrucciones **Write** con información no relacionada producirán un registro difícil de leer.  Por otro lado, usar **WriteLine** para colocar instrucciones relacionadas en líneas independientes puede hacer que sea difícil distinguir la información del mismo tipo.  En general, utilice varias instrucciones **Write** cuando desee combinar información de varios orígenes para crear un único mensaje informativo y utilice la instrucción **WriteLine** cuando desee crear un único mensaje completo.  
  
### Para escribir una línea completa  
  
1.  Llame al método <xref:System.Diagnostics.Trace.WriteLine%2A> o <xref:System.Diagnostics.Trace.WriteLineIf%2A>.  
  
     Se agrega un retorno de carro al final del mensaje que devuelve este método, para que el siguiente mensaje devuelto por **Write**, **WriteIf**, **WriteLine** o **WriteLineIf** comience en la línea siguiente:  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteLine("Error in AppendData procedure.")  
    Trace.WriteLineIf(errorFlag, "Error in AppendData procedure.")  
  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteLine ("Error in AppendData procedure.");  
    System.Diagnostics.Trace.WriteLineIf(errorFlag,   
       "Error in AppendData procedure.");  
  
    ```  
  
### Para escribir una línea parcial  
  
1.  Llame al método <xref:System.Diagnostics.Trace.Write%2A> o <xref:System.Diagnostics.Trace.WriteIf%2A>.  
  
     El siguiente mensaje generado por **Write**, **WriteIf**, **WriteLine** o **WriteLineIf** empezará en la misma línea que el mensaje generado por la instrucción **Write** o **WriteIf**:  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteIf(errorFlag, "Error in AppendData procedure.")  
    Debug.WriteIf(errorFlag, "Transaction abandoned.")  
    Trace.Write("Invalid value for data request")  
  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteIf(errorFlag,   
       "Error in AppendData procedure.");  
    System.Diagnostics.Debug.WriteIf(errorFlag, "Transaction abandoned.");  
    Trace.Write("Invalid value for data request");  
  
    ```  
  
### Para comprobar que se cumplen ciertas condiciones antes o después de ejecutar un método  
  
1.  Llame al método <xref:System.Diagnostics.Trace.Assert%2A>.  
  
    ```vb  
    Dim I As Integer = 4  
    Trace.Assert(I = 5, "I is not equal to 5.")  
  
    ```  
  
    ```csharp  
    int I = 4;  
    System.Diagnostics.Trace.Assert(I == 5, "I is not equal to 5.");  
  
    ```  
  
    > [!NOTE]
    >  Puede usar **Assert** con la depuración y la traza.  Este ejemplo envía la pila de llamadas a cualquier agente de escucha de la colección **Agentes de escucha**.  Para obtener más información, consulte [Aserciones en el código administrado](../Topic/Assertions%20in%20Managed%20Code.md) y <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Diagnostics.Debug.WriteIf%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.Debug.WriteLineIf%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.Trace.WriteIf%2A?displayProperty=fullName>   
 <xref:System.Diagnostics.Trace.WriteLineIf%2A?displayProperty=fullName>   
 [Tracing and Instrumenting Applications](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)   
 [How to: Create, Initialize and Configure Trace Switches](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)   
 [Trace Switches](../../../docs/framework/debug-trace-profile/trace-switches.md)   
 [Trace Listeners](../../../docs/framework/debug-trace-profile/trace-listeners.md)