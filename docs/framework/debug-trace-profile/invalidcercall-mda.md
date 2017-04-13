---
title: "invalidCERCall MDA | Microsoft Docs"
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
  - "invalid CER calls"
  - "InvalidCERCall MDA"
  - "MDAs (managed debugging assistants), CER calls"
  - "constrained execution regions"
  - "CER calls"
  - "managed debugging assistants (MDAs), CER calls"
ms.assetid: c4577410-602e-44e5-9dab-fea7c55bcdfe
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# invalidCERCall MDA
El asistente para la depuración administrada \(MDA\) `invalidCERCall` se activa cuando hay una llamada dentro de un gráfico de área de ejecución restringida \(CER\) a un método que no tiene contrato de confiabilidad o a un contrato excesivamente débil.  Un contrato débil es aquél que declara que el estado de daño del peor caso tiene un ámbito mayor que el de la instancia pasada a la llamada, es decir, el <xref:System.AppDomain> o estado del proceso puede quedar dañado o su resultado no es siempre calculable determinísticamente cuando se lo llama dentro de una CER.  
  
## Síntomas  
 Resultados inesperados al ejecutar el código en una CER.  Los síntomas no son específicos.  Podrían ser una <xref:System.OutOfMemoryException> inesperada, una <xref:System.Threading.ThreadAbortException> u otras excepciones en la llamada al método no confiable porque el motor en tiempo de ejecución no lo preparó con suficiente adelanto o protegerlo de las excepciones <xref:System.Threading.ThreadAbortException> en tiempo de ejecución.  Una mayor amenaza es que cualquier excepción resultante del método en tiempo de ejecución podría dejar el <xref:System.AppDomain> o el proceso en un estado inestable, lo cual es contrario al objetivo de una CER.  El motivo de crear una CER es evitar daños como este en el estado.  Los síntomas de estado dañado son específicos de las aplicaciones porque la definición de estado coherente es distinta de unas aplicaciones a otras.  
  
## Motivo  
 El código contenido en una CER llama a una función sin <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> o con un <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> débil que no es compatible con la ejecución en una CER.  
  
 En términos de sintaxis de contrato de confiabilidad, un contrato débil es aquél que no especifica un valor de enumeración <xref:System.Runtime.ConstrainedExecution.Consistency> o que especifica un valor <xref:System.Runtime.ConstrainedExecution.Consistency> de <xref:System.Runtime.ConstrainedExecution.Consistency>, <xref:System.Runtime.ConstrainedExecution.Consistency> o <xref:System.Runtime.ConstrainedExecution.Cer>.  Cualquiera de estas condiciones indica que el código llamado puede impedir los esfuerzos del otro código de la CER para mantener el estado coherente.  Las CER permiten al código tratar los errores de una forma muy determinista, manteniendo invariables internas que son importantes para la aplicación y permitiéndole continuar en ejecución cuando se presentan errores transitorios como excepciones por memoria insuficiente.  
  
 La activación de este MDA indica que hay posibilidades de que el método llamado en la CER puede producir errores de una forma que no esperaba el llamador o que deja el <xref:System.AppDomain> o el proceso en estado dañado o irrecuperable.  Por supuesto, el código llamado podría ejecutarse correctamente y el problema es simplemente que falta un contrato.  Sin embargo, los problemas relacionados con la escritura de código fiable son muy sutiles y la ausencia de un contrato es un buen indicador de que el código podría no ejecutarse correctamente.  Los contratos son indicadores de que el programador ha escrito el código de forma confiable y además prometen que estas garantías no cambiarán en futuras revisiones del código.  Es decir, los contratos son declaraciones de intenciones y no sólo detalles de implementación.  
  
 Puesto que cualquier método con un contrato débil o inexistente puede producir errores de muchas maneras impredecibles, el tiempo de ejecución no intenta quitar ninguno de sus propios errores impredecibles causados por una compilación JIT lenta, un relleno de diccionario genérico o anulaciones de subprocesos, por ejemplo.  Es decir, cuando se activa este MDA, indica que el tiempo de ejecución no incluyó el método llamado en la CER que se está definiendo; el gráfico de llamadas se terminó en este nodo porque continuar la preparación de este subárbol ayudaría a ocultar el posible error.  
  
## Resolución  
 Agregue a la función un contrato de confiabilidad válido o evite utilizar esa llamada a la función.  
  
## Efecto en el Runtime  
 El efecto de llamar a un contrato débil desde una CER podría ser que la CER no pudiera finalizar sus operaciones.  Esto podría producir daños en el estado del proceso de <xref:System.AppDomain>.  
  
## Resultados  
 Lo siguiente es un ejemplo de los resultados de este MDA.  
  
 `Method 'MethodWithCer', while executing within a constrained execution region, makes a call at IL offset 0x000C to 'MethodWithWeakContract', which does not have a sufficiently strong reliability contract and might cause non-deterministic results.`  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>   
 <xref:System.Runtime.ConstrainedExecution>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)