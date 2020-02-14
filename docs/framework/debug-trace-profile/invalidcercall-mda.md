---
title: MDA de invalidCERCall
ms.date: 03/30/2017
helpviewer_keywords:
- invalid CER calls
- InvalidCERCall MDA
- MDAs (managed debugging assistants), CER calls
- constrained execution regions
- CER calls
- managed debugging assistants (MDAs), CER calls
ms.assetid: c4577410-602e-44e5-9dab-fea7c55bcdfe
ms.openlocfilehash: f8e467401f7c50898613c7cf6eca68a8a705431a
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217395"
---
# <a name="invalidcercall-mda"></a>MDA de invalidCERCall
El Asistente para la depuración administrada (MDA) `invalidCERCall` se activa cuando hay una llamada desde el gráfico de región de ejecución restringida (CER) a un método que no tiene ningún contrato de confiabilidad o un contrato excesivamente débil. Un contrato débil es el que declara que el peor caso de daño de estado tiene un ámbito mayor que la instancia que se pasa a la llamada, es decir, el estado de <xref:System.AppDomain> o del proceso puede resultar dañado o su resultado no siempre se puede calcular de forma determinista cuando se llama desde dentro de una CER.  
  
## <a name="symptoms"></a>Síntomas  
 Resultados inesperados cuando se ejecuta código en una CER. Los síntomas no son específicos. Podría ser una excepción <xref:System.OutOfMemoryException>, <xref:System.Threading.ThreadAbortException> inesperada o de otro tipo en la llamada al método no confiable porque el tiempo de ejecución no lo preparó por adelantado ni lo protegió de excepciones <xref:System.Threading.ThreadAbortException> en tiempo de ejecución. Una amenaza mayor es que cualquier excepción resultante del método en tiempo de ejecución podría dejar al <xref:System.AppDomain> o al proceso en un estado inestable, lo que contradice el objetivo de una CER. El motivo por el que se crea una CER es para evitar este tipo de daños de estado. Los síntomas de estado dañado son específicos de la aplicación porque la definición de estado coherente es diferente entre aplicaciones.  
  
## <a name="cause"></a>Causa  
 El código dentro de una CER llama a una función sin <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> o con un <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> débil que no es compatible con la ejecución en una CER.  
  
 En cuanto a la sintaxis de contratos de confiabilidad, un contrato débil es el que no especifica un valor de enumeración <xref:System.Runtime.ConstrainedExecution.Consistency> o especifica un valor <xref:System.Runtime.ConstrainedExecution.Consistency> de <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptProcess>, <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptAppDomain>, o <xref:System.Runtime.ConstrainedExecution.Cer.None>. Cualquiera de estas condiciones indica que el código que se llama puede impedir los esfuerzos del otro código de la CER para mantener un estado coherente.  Las CER permiten al código tratar los errores de una manera muy determinista, manteniendo invariables internas que son importantes para la aplicación y permitiendo que se siga ejecutando en presencia de errores transitorios como excepciones de memoria insuficiente.  
  
 La activación de este MDA indica una posibilidad de que el método que se llama en la CER pueda producir un error que el autor de la llamada no esperaba o que deje el estado de <xref:System.AppDomain> o del proceso dañado o irrecuperable. Por supuesto, es posible que el código llamado se ejecute correctamente y el problema sea simplemente un contrato que falta. Pero los problemas implicados en la escritura de código confiable son sutiles y la ausencia de un contrato es un buen indicador de que es posible que el código no se ejecute correctamente. Los contratos son indicadores de que el programador ha codificado de forma confiable y además promete que estas garantías no cambiarán en revisiones futuras del código.  Es decir, los contratos son declaraciones de intención y no solo detalles de implementación.  
  
 Dado que cualquier método con un contrato débil o inexistente puede producir errores de muchas maneras impredecibles, el tiempo de ejecución no intenta eliminar del método ninguno de sus propios errores impredecibles que se introducen mediante la compilación JIT lenta, la especificación de diccionarios genéricos o la anulación de subprocesos, por ejemplo. Es decir, cuando se activa este MDA, indica que el tiempo de ejecución no incluyó el método llamado en la CER que se está definiendo; el gráfico de llamadas se terminó en este nodo porque continuar la preparación de este subárbol ayudaría a ocultar el posible error.  
  
## <a name="resolution"></a>Solución  
 Agregar un contrato de confiabilidad válido a la función o evitar usar esa llamada de función.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 El efecto de llamar a un contrato débil desde una CER podría ser que la CER no pueda completar sus operaciones. Esto podría provocar daños en el estado de proceso del <xref:System.AppDomain>.  
  
## <a name="output"></a>Output  
 A continuación puede ver un resultado de ejemplo de este MDA.  
  
 `Method 'MethodWithCer', while executing within a constrained execution region, makes a call at IL offset 0x000C to 'MethodWithWeakContract', which does not have a sufficiently strong reliability contract and might cause non-deterministic results.`  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution>
- [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](diagnosing-errors-with-managed-debugging-assistants.md)
